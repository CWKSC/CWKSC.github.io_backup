---
date: 2020-06-15 00:00:00
layout: post
title: "離散數學 命題邏輯 規則 Discrete Mathematics Propositional Logic Rule"
subtitle: 
description: "命題邏輯的一些規則：Logical Equivalences 邏輯等價, Rules of Inference 推理規則"
image: https://cdn.jsdelivr.net/gh/CWKSC/MyResources/Image/post11.jpg
optimized_image: https://cdn.jsdelivr.net/gh/CWKSC/MyResources/Image/optimized/post11_opt.jpg
category: Discrete Mathematics
tags: 
  - Mathematics 數學
  - Discrete Mathematics 離散數學
  - Propositional Logic 命題邏輯
author: CWKSC
paginate: false
math: true
---

# Logical Equivalences

### Identity laws

$$
p \wedge \top \equiv p \\
p\vee \bot \equiv p \\
$$

### Domination laws

$$
p\vee \top \equiv \top \\
p\wedge \bot \equiv \bot
$$

### Idempotent or tautology laws

$$
p \vee p \equiv p\\
p \wedge p \equiv p
$$

### Double negation law

$$
\lnot (\lnot p) ≡ p
$$

### Commutative laws

$$
p \vee q \equiv q \vee p \\
p \wedge q \equiv q \wedge p
$$

### Associative laws

$$
(p\vee q)\vee r\equiv p\vee (q\vee r)\\
(p\wedge q)\wedge r\equiv p\wedge (q\wedge r)
$$

### Distributive laws

$$
p\vee (q\wedge r)\equiv (p\vee q)\wedge (p\vee r) \\
p\wedge (q\vee r)\equiv (p\wedge q)\vee (p\wedge r)
$$

### De Morgan's laws

$$
\neg (p\wedge q)\equiv \neg p\vee \neg q \\
\neg (p\vee q)\equiv \neg p\wedge \neg q
$$

### Absorption laws

$$
p\vee (p\wedge q)\equiv p\\
p\wedge (p\vee q)\equiv p
$$

### Negation laws

$$
p\vee \neg p\equiv \top\\
p\wedge \neg p\equiv \bot
$$

## Logical Equivalences Involving Conditional Statements

$$
p\rightarrow q\equiv \neg p\vee q\\
p\rightarrow q\equiv \neg q\rightarrow \neg p\\
p\vee q\equiv \neg p\rightarrow q\\
p\wedge q\equiv \neg (p\rightarrow \neg q)\\
\neg (p\rightarrow q)\equiv p\wedge \neg q\\
(p\rightarrow q)\wedge (p\rightarrow r)\equiv p\rightarrow (q\wedge r)\\
(p\rightarrow q)\vee (p\rightarrow r)\equiv p\rightarrow (q\vee r)\\
(p\rightarrow r)\wedge (q\rightarrow r)\equiv (p\vee q)\rightarrow r\\
(p\rightarrow r)\vee (q\rightarrow r)\equiv (p\wedge q)\rightarrow r
$$

## Logical Equivalences Involving Biconditional Statements

$$
p\leftrightarrow  q\equiv (p\rightarrow q)\wedge (q\rightarrow p)\\
p\leftrightarrow  q\equiv \neg p\leftrightarrow  \neg q\\
p\leftrightarrow  q\equiv (p\wedge q)\vee (\neg p\wedge \neg q)\\
\neg (p\leftrightarrow  q)\equiv p\leftrightarrow  \neg q
$$

# Rules of Inference

### Modus ponens

$$
p\\
p \rightarrow q\\
\therefore q
$$

### Modus tollens

$$
\lnot q\\
p \rightarrow q\\
\therefore \lnot p
$$

### Hypothetical syllogism

$$
p \rightarrow q\\
q \rightarrow r \\
\therefore p \rightarrow r
$$

### Disjunctive syllogism

$$
p \vee q\\
\lnot p\\
\therefore q
$$

### Addition

$$
p\\
\therefore p \vee q
$$

### Simplification

$$
p \wedge q\\
\therefore p
$$

### Conjunction

$$
p\\
q\\
\therefore p \wedge q
$$

### Resolution

$$
p \vee q\\
\lnot p \vee r\\
\therefore q \vee r
$$

## Rules of Inference for Quantified Statements

### Universal instantiation

$$
\forall x P(x)\\
\therefore P(c)
$$

### Universal generalization

$$
P (c) \space for \space an \space arbitrary\space  c\\
\therefore \forall x P(x)
$$

### Existential instantiation

$$
\exists x P(x)\\
\therefore P(x) \space for \space some \space element \space c
$$

### Existential generalization

$$
P(x) \space for \space some \space element \space c\\
\therefore \exists x P(x)
$$

# Reference

https://en.wikipedia.org/wiki/Logical_equivalence

https://en.wikipedia.org/wiki/Rule_of_inference