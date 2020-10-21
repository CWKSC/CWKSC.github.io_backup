---
date: 2020-09-25 20:00:00
layout: post
title: "命題邏輯 Logical Equivalences 邏輯等價, Rules of Inference 推理規則"
subtitle: 
description: "命題邏輯的一些規則：Logical Equivalences 邏輯等價, Rules of Inference 推理規則"
image: https://cdn.jsdelivr.net/gh/CWKSC/MyResources/Image/post11.jpg
optimized_image: https://cdn.jsdelivr.net/gh/CWKSC/MyResources/Image/optimized/post11_opt.jpg
category: Discrete Mathematics
tags: 
  - Mathematics 數學
  - Discrete Math 離散數學
  - PropositionalLogic 命題邏輯
author: CWKSC
paginate: false
math: true
---

命題邏輯的 Logical Equivalences 邏輯等價, Rules of Inference 推理規則

## Logical Equivalences

$$
\displaylines{
\begin{array}{|c|c|c|}
\hline
  \text{Equivalence} & \text{Name} \\ 
\hline
   \mathbb{\displaylines{p \wedge \top \equiv p \\
p\vee \bot \equiv p}} & \text{Identity laws}\\
\hline
   \mathbb{\displaylines{p\vee \top \equiv \top \\\
p\wedge \bot \equiv \bot}} & \text{Domination laws}\\
\hline
   \mathbb{\displaylines{p \vee p \equiv p\\\
p \wedge p \equiv p}} & \text{Idempotent or tautology laws}\\ 
\hline
   \mathbb{\displaylines{\lnot (\lnot p) \equiv p}} & \text{Double negation law}\\
\hline
   \mathbb{\displaylines{p \vee q \equiv q \vee p \\\
p \wedge q \equiv q \wedge p}} & \text{Commutative laws} \\
\hline
   \mathbb{\displaylines{(p\vee q)\vee r\equiv p\vee (q\vee r)\\\
(p\wedge q)\wedge r\equiv p\wedge (q\wedge r)}} & \text{Associative laws}\\ 
\hline
   \mathbb{\displaylines{p\vee (q\wedge r)\equiv (p\vee q)\wedge (p\vee r) \\\
p\wedge (q\vee r)\equiv (p\wedge q)\vee (p\wedge r)}} & \text{Distributive laws} \\ 
\hline
    \mathbb{\displaylines{\neg (p\wedge q)\equiv \neg p\vee \neg q \\\
\neg (p\vee q)\equiv \neg p\wedge \neg q}} & \text{De Morgan's laws} \\
\hline
    \mathbb{\displaylines{p\vee (p\wedge q)\equiv p\\\
p\wedge (p\vee q)\equiv p}} & \text{Absorption laws}\\
\hline
    \mathbb{\displaylines{p\vee \neg p\equiv \top\\\
p\wedge \neg p\equiv \bot}} & \text{Negation laws}\\
    \hline
\end{array}
}
$$

### Logical Equivalences Involving Conditional Statements

$$
\displaylines{
\begin{aligned}
p\rightarrow q &\equiv \neg p\vee q\\\
p\rightarrow q &\equiv \neg q\rightarrow \neg p\\\
p\vee q&\equiv \neg p\rightarrow q\\\
p\wedge q&\equiv \neg (p\rightarrow \neg q)\\\
\neg (p\rightarrow q)&\equiv p\wedge \neg q\\\
(p\rightarrow q)\wedge (p\rightarrow r)&\equiv p\rightarrow (q\wedge r)\\\
(p\rightarrow q)\vee (p\rightarrow r)&\equiv p\rightarrow (q\vee r)\\\
(p\rightarrow r)\wedge (q\rightarrow r)&\equiv (p\vee q)\rightarrow r\\\
(p\rightarrow r)\vee (q\rightarrow r)&\equiv (p\wedge q)\rightarrow r
\end{aligned}
}
$$

### Logical Equivalences Involving Biconditional Statements

$$
\displaylines{
\begin{aligned}
p\leftrightarrow  q&\equiv (p\rightarrow q)\wedge (q\rightarrow p)\\\
p\leftrightarrow  q&\equiv \neg p\leftrightarrow  \neg q\\\
p\leftrightarrow  q&\equiv (p\wedge q)\vee (\neg p\wedge \neg q)\\\
\neg (p\leftrightarrow  q)&\equiv p\leftrightarrow  \neg q
\end{aligned}}
$$

## Rules of Inference

$$
\displaylines{
\begin{array} {|c|c|}\hline Rule \space of\space Inference & Name \\ 
\hline 
\displaylines{p \\ \underline{p \rightarrow q} \\ \therefore q} & \text{Modus ponens} \\ 
\hline 
\displaylines{\lnot q \\ \underline{p \rightarrow q} \\ \therefore \lnot p}& \text{Modus tollens} \\ 
\hline 
\displaylines{p \rightarrow q \\ \underline{q \rightarrow r} \\ \therefore p \rightarrow r }& \text{Hypothetical syllogism} \\ 
\hline
\displaylines{p \vee q\\ \lnot p \\ \overline{\therefore q}} & \text{Disjunctive syllogism} \\ 
\hline 
\displaylines{p \\ \overline{\therefore p \vee q}} & \text{Addition} \\ 
\hline
\displaylines{\underline{p \wedge q}\\ \therefore p }& \text{Simplification} \\ 
\hline 
\displaylines{p\\ q\\ \overline{\therefore p \wedge q} }& \text{Conjunction} \\
\hline 
\displaylines{p \vee q\\ \lnot p \vee r\\ \overline{\therefore q \vee r}} & \text{Resolution} \\ \hline
\end{array}
}
$$

### Rules of Inference for Quantified Statements

$$
\displaylines{
\begin{array} {|c|c|}
\hline 
Rule \space of \space Inference & Name \\ 
\hline 
\displaylines{\forall x P(x) \\ \therefore P(c)}& \text{Universal instantiation} \\
\hline 
\displaylines{P (c) \space for \space an \space arbitrary\space c \\ \therefore \forall x P(x)} & \text{Universal generalization} \\
\hline
\displaylines{\exists x P(x) \\\ \therefore P(x) \space for \space some \space element \space c }& \text{Existential instantiation} \\
\hline 
\displaylines{P(x) \space for \space some \space element \space c\\\ \therefore \exists x P(x)} & \text{Existential generalization}\\
\hline
\end{array}
}
$$

## Reference

[Logical equivalence - Wikipedia](https://en.wikipedia.org/wiki/Logical_equivalence)

[Rule of inference - Wikipedia](https://en.wikipedia.org/wiki/Rule_of_inference)