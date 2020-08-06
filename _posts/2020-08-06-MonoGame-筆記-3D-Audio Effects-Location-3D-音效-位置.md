---
date: 2020-08-06 16:00:00
layout: post
title: "MonoGame 筆記 3D Audio Effects - Location 3D 音效 - 位置"
subtitle: 
description: "MonoGame 筆記，3D 音效 - 位置，只是筆記，搬運自知乎"
image: https://cdn.jsdelivr.net/gh/CWKSC/MyResources/Image/post10.jpg
optimized_image: https://cdn.jsdelivr.net/gh/CWKSC/MyResources/Image/optimized/post10_opt.jpg
category: MonoGame
tags:
  - MonoGame
  - C#
author: CWKSC
paginate: false
---

只是筆記，搬運自：

[MonoGame 笔记 - 3D Audio Effects - Location / 3D 音效-位置 - 知乎](https://zhuanlan.zhihu.com/p/96935153)

___

做個 Google 翻譯

[3D Audio Effects - Location - RB Whitaker's Wiki](http://rbwhitaker.wikidot.com/3d-audio-effects-location)

## ▌3D Audio Effects - Location / 3D 音效 - 位置

### ▌Overview 概觀

本教程以及緊隨其後的教程將討論 3D 音頻效果的一些基礎知識。我們將在本教程開始時簡要介紹一下什麼是3D音頻效果以及何時需要使用它們。然後，我們將在本教程的其餘部分中研究如何執行簡單的3D音頻效果。我們將使聲音提示看起來好像來自某個空間點

如果您還沒有使用 XACT 進行任何操作，則可能應該閱讀有關使用 XACT 和在 XNA 中播放聲音的教程。另外，當我製作本教程時，我使用了 XACT 聲音循環教程中的信息。您將不需要它，但是無論如何它可能會派上用場

### ▌3D 音效

3D 音頻效果只是改變聲音的播放方式，給人一種幻覺，即它們正在 3D 空間中發生。換句話說，爆炸不僅是遊戲中的爆炸，而且玩家可以知道爆炸發生的位置

3D 音頻效果可幫助玩家感覺更多地參與遊戲。他們覺得聲音是從周圍傳來的，而不僅僅是來自計算機屏幕

3D 音頻效果還可以讓玩家指示事件發生的位置。假設您正在玩第一人稱射擊遊戲，而有人正在向您射擊。沒有 3D 效果，您將能夠聽到自己被槍殺的情況。不過，有了 3D 音頻效果，您就可以分辨出另一個播放器在哪裡，並且您會知道用哪種方法找到它們

我所見過的關於 3D 音頻效果可以做什麼的最酷的例子之一是 Virtual Barbershop。我已在下面添加了“視頻”。如果使用耳機，並且閉上眼睛，效果最佳。試試看！

*【視頻請去原網站觀看】*

### ▌Setup 設置

稍後，我們將討論如何編寫執行 3D 音頻效果的代碼。您可以使用任何聲音提示執行這些效果。不過，我覺得最好解釋一下本教程中使用的內容。

為此，您將需要已經準備好使用 XACT 項目。（而且它至少必須有一個聲音提示！）如果您還沒有這樣做，請看一下有關使用 XACT 的教程

我選擇了一種聲音效果，它只是可以循環飛行的直升機。我希望它循環播放，以便在聲音的來源四處移動時，聲音可以一直傳下去（聽起來不錯）。我在 [http://flashkit.com](http://www.flashkit.com/) 上找到了聲音效果。該鏈接應該鏈接到上面的頁面，但是如果鏈接斷開，您應該可以通過在其 “Sound FX” 頁面上搜索 "Helicopter Loop” 來再次找到它。另外，我已經將直升機提示設置為永遠循環，如聲音循環教程中所述

最後，我已經編寫了播放直升機聲音的代碼，沒有任何 3D 音頻效果，如 “播放聲音” 教程中所述

## ▌Coding the Effect

我們需要做的第一件事是獲得聲音提示的參考。這意味著我們還希望告訴我們的聲音提示以稍微不同的方式播放。因此，首先，將以下行作為實例變量添加到我們的遊戲中：

```csharp
private Cue cue;
```

現在轉到您告訴聲音播放的地方。我們將要更改此設置。該代碼曾經說過：

```csharp
soundBank.PlayCue("helicopter");
```

我們要將其更改為：

```csharp
cue = soundBank.GetCue("helicopter");
cue.Play();
```

此時，您應該能夠再次運行您的遊戲，並且它應該像以前一樣正常工作

現在讓我們繼續下一步：告訴我們的遊戲聲音從哪裡發出，聽眾在哪裡。我將進行遊戲設置，以使聲音源在聽眾周圍繞圈移動。為此，我要做的第一件事是將以下代碼作為實例變量添加到主遊戲類：

```csharp
private AudioEmitter emitter = new AudioEmitter();
private AudioListener listener = new AudioListener();

private float angle = 0;
private float distance = 5;
```

AudioEmitter 類將告訴我們有關發射器的信息。在本教程中，我們將僅查看發射器的位置，但是您可以嘗試使用其他幾個選項。 AudioListener 類將指定有關偵聽器（播放器）所在位置的類似信息。角度和距離變量將用於計算發射器圍繞偵聽器旋轉時的位置

接下來，我創建了一種將發射器的角度和距離轉換為 3D 空間中 Vector3 位置的方法，如下所示：

```csharp
private Vector3 CalculateLocation(float angle, float distance)
{
    return new Vector3(
        (float)Math.Cos(angle) * distance,
        0,
        (float)Math.Sin(angle) * distance);
}
```

此方法基本上將極坐標轉換為笛卡爾坐標（如果您想了解更多有關此知識，請參閱坐標系統上的數學教程）。

接下來，我將以下代碼添加到我的 `Update()` 方法中。這是將更改我的音頻發射器位置的代碼，並且還告訴提示應用新的 3D 音頻效果：

```csharp
angle += 0.01f;  // rotate the emitter around a little bit
listener.Position = Vector3.Zero;  // the listener just stays at the origin the whole time
emitter.Position = CalculateLocation(angle, distance);  // calculate the location of the emitter again

cue.Apply3D(listener, emitter); // apply the 3D transform to the cue
```

這應該做我們需要做的所有事情。我們只剩下一個零錢。如果要對提示對象應用 3D 效果，則必須在告訴提示播放之前告訴它在某個點上應用 3D 效果。它會以不同的方式初始化提示。因此，在告訴提示開始播放之前，請確保添加類似以下代碼的內容：

```csharp
// tell it to apply a 3D transform even before you play the cue
cue.Apply3D(listener, emitter);
 
// and then you can tell it to start playing
cue.Play();
```

有了這些，您現在應該可以播放項目並聽到聲音在移動了！我在下面添加了我項目的所有代碼，因為我意識到這是一個複雜的教程。它引入了其他多個教程中的內容，添加了新內容

## ▌Show full code 顯示完整代碼

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Microsoft.Xna.Framework;
using Microsoft.Xna.Framework.Audio;
using Microsoft.Xna.Framework.Content;
using Microsoft.Xna.Framework.GamerServices;
using Microsoft.Xna.Framework.Graphics;
using Microsoft.Xna.Framework.Input;
using Microsoft.Xna.Framework.Media;
 
namespace SoundDemo
{
    /// <summary>
    /// This is the main type for your game
    /// </summary>
    public class Game1 : Microsoft.Xna.Framework.Game
    {
        GraphicsDeviceManager graphics;
        SpriteBatch spriteBatch;
 
        private AudioEngine audioEngine;
        private WaveBank waveBank;
        private SoundBank soundBank;
 
        private Cue cue;
 
        private AudioEmitter emitter = new AudioEmitter();
        private AudioListener listener = new AudioListener();
 
        private float angle = 0;
        private float distance = 5;
 
        public Game1()
        {
            graphics = new GraphicsDeviceManager(this);
            Content.RootDirectory = "Content";
        }
 
        /// <summary>
        /// Allows the game to perform any initialization it needs to before starting to run.
        /// This is where it can query for any required services and load any non-graphic
        /// related content.  Calling base.Initialize will enumerate through any components
        /// and initialize them as well.
        /// </summary>
        protected override void Initialize()
        {
            // TODO: Add your initialization logic here
 
            base.Initialize();
        }
 
        /// <summary>
        /// LoadContent will be called once per game and is the place to load
        /// all of your content.
        /// </summary>
        protected override void LoadContent()
        {
            // Create a new SpriteBatch, which can be used to draw textures.
            spriteBatch = new SpriteBatch(GraphicsDevice);
 
            LoadAudioContent();
        }
 
        private void LoadAudioContent()
        {
            audioEngine = new AudioEngine("Content/Sound/SoundDemoAudio.xgs");
            waveBank = new WaveBank(audioEngine, "Content/Sound/Wave Bank.xwb");
            soundBank = new SoundBank(audioEngine, "Content/Sound/Sound Bank.xsb");
 
            cue = soundBank.GetCue("helicopter");
 
            // tell it to apply a 3D transform even before you play the cue
            cue.Apply3D(listener, emitter);
 
            // and then you can tell it to start playing
            cue.Play();
        }
 
        private Vector3 CalculateLocation(float angle, float distance)
        {
            return new Vector3(
                (float)Math.Cos(angle) * distance,
                0,
                (float)Math.Sin(angle) * distance);
        }
 
        /// <summary>
        /// UnloadContent will be called once per game and is the place to unload
        /// all content.
        /// </summary>
        protected override void UnloadContent()
        {
            // TODO: Unload any non ContentManager content here
        }
 
        /// <summary>
        /// Allows the game to run logic such as updating the world,
        /// checking for collisions, gathering input, and playing audio.
        /// </summary>
        /// <param name="gameTime">Provides a snapshot of timing values.</param>
        protected override void Update(GameTime gameTime)
        {
            // Allows the game to exit
            if (GamePad.GetState(PlayerIndex.One).Buttons.Back == ButtonState.Pressed)
                this.Exit();
 
            angle += 0.01f;  // rotate the emitter around a little bit
            listener.Position = Vector3.Zero;  // the listener just stays at the origin the whole time
            emitter.Position = CalculateLocation(angle, distance);  // calculate the location of the emitter again
 
            cue.Apply3D(listener, emitter); // apply the 3D transform to the cue
 
            audioEngine.Update();
 
            base.Update(gameTime);
        }
 
        /// <summary>
        /// This is called when the game should draw itself.
        /// </summary>
        /// <param name="gameTime">Provides a snapshot of timing values.</param>
        protected override void Draw(GameTime gameTime)
        {
            GraphicsDevice.Clear(Color.CornflowerBlue);
 
            // TODO: Add your drawing code here
 
            base.Draw(gameTime);
        }
    }
}
```

## ▌What's Next? 下一步

您可能將會發現查看 [3D Audio Effects - Attenuation - RB Whitaker's Wiki](http://rbwhitaker.wikidot.com/3d-audio-effects-attenuation) "在 3D 音頻影響中使用衰減” 的教程很有用，該教程告訴您如何使 XNA 根據與聽眾的距離來改變聲音的大小 