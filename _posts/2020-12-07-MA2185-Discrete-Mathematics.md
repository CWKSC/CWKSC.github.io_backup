---
date: 2020-12-08 00:00:00
layout: post
title: "MA2185 Discrete Mathematics"
subtitle: 
description: "MA2185 Discrete Mathematics 離散數學"
image: https://cdn.jsdelivr.net/gh/CWKSC/MyResources/Image/post12.jpg
optimized_image: https://cdn.jsdelivr.net/gh/CWKSC/MyResources/Image/optimized/post12_opt.jpg
category: Discrete Mathematics
tags: 
  - Mathematics 數學
  - Discrete Math 離散數學
author: CWKSC
paginate: false
math: true
---

Note of MA2185 Discrete Mathematics

### 1.1 Propositional Logic

**Negation ¬p, Conjunction p ∧ q, Disjunction p ∨ q, Exclusive or p ⊕ q**

**Conditional statement p → q** 

p is called the **hypothesis** (or antecedent or premise) 假設/前提

q is called the **conclusion** (or consequence) 結論/結果

**Biconditional statement p ↔ q**

### **1.3 Propositional Equivalences**

Always true, **tautology (重言式)** 

Always false, **contradiction(矛盾式)**

Neither a tautology nor contradiction, **contingency(可能式)**

**Logically equivalent,** **p ≡ q**, if p ↔ q is a tautology

**De Morgan’s Laws**


$$
¬(p ∧ q) ≡ ¬p ∨ ¬q\\
¬(p ∨ q) ≡ ¬p ∧ ¬q
$$

### **1.4 Predicates and Quantifiers**

**Universal quantifier** ∀, **Existential quantification** ∃

Counterexample 反例


$$
¬∀xP (x) ≡ ∃x ¬P (x)\\
¬∃xQ(x) ≡ ∀x ¬Q(x)
$$

### **1.6 Rules of Inference**

[命題邏輯 Logical Equivalences 邏輯等價, Rules of Inference 推理規則](https://cwksc.github.io/DiscreteMathematics_PropositionalLogic_basic/)

### **2.1 Sets**

a is element of set A, a ∈ A


$$
\begin{align}
&\N = \{0, 1, 2, 3,...\},\text{ the set of natural numbers 自然數}\\

&\Z = \{..., −2, −1, 0, 1, 2,...\}, \text{the set of integers 整數}\\

&\Q = \{p/q \| p ∈ Z, q ∈ Z, and q = 0\}, \text{the set of rational numbers 有理數}\\

&\R,\text{ the set of real numbers 實數}\\

&\C, \text{ the set of complex numbers 虛數}
\end{align}
$$
Closed interval [a, b], open interval (a, b)

A and B are **equal** if and only if $$∀x(x ∈ A ↔ x ∈ B)$$

Set A is **subset** of set B, $$A ⊆ B, ∀x(x ∈ A → x ∈ B)$$

A ⊆ B and B ⊆ A, then A = B

For every set S, ∅ ⊆ S and S ⊆ S

S is **finite set**, n distinct elements, n is **cardinality (基數)** of |S|

Power set of S is the set of all subsets of the set S. denoted P(S)
$$
P(\{0, 1, 2\}) = \text{ \{∅,\{0\},\{1\},\{2\},\{0, 1\},\{0, 2\},\{1, 2\},\{0, 1, 2\} \}}
$$


**Cartesian product (笛卡爾積),** $$A × B = {(a, b) \| a ∈ A ∧ b ∈ B}$$

**Truth set,** $${x \| P (x)}$$ 

### **2.2 Set Operations**

**Union A ∪ B, Intersection A ∩ B, Difference A − B, Complement** **A**

$$
|A ∪ B| = |A| + |B| - |A ∩ B|
$$
Two sets are called disjoint if their intersection is the empty set

### **2.3 Functions**

**[One-to-one, Injunction]**

$$f (a) = f (b)$$ implies that a = b for all a and b in the domain of f.

$$
∀a∀b( f(a) = f(b) → a = b), ∀a∀b( a  b → f(a) = f(b) )
$$
**[Onto, Surjection]**

For every element b ∈ B there an element a ∈ A with f (a) = b

$$∀y∃x(f (x) = y)$$, where x is the domain and y is the codomain

**[One-to-one correspondence, Bijection]** 

Both one-to-one and onto

**[Increasing]** $$f (x) ≤ f (y)$$, **[Strictly increasing]** $$f (x) < f (y)$$

**[Decreasing]** $$f (x) ≥ f (y)$$, **[Strictly decreasing]** $$f (x) > f (y)$$

**[Composition of functions]** **(f ◦ g)(a) = f(g(a))**

If f and g are injective/surjective, then f ◦ g is injective/surjective. 

**[Identity functions]** 
$$
Id_A(a) = a
$$
**[Inverse functions]** 
$$
f:A → B\\ f^{-1}:B → A
$$

$$
\text{f is injective, g ◦ f = }Id_A\text{,  f is surjective, f ◦ g =} Id_B\\
\text{f is bijective, g ◦ f = }Id_A \text{ and  f ◦ g = } Id_B 
$$

Let f be a function from the set A to the set B. The **graph** of the function f is the set of ordered pairs {(a, b) | a ∈ A and f (a) = b}.

A **partial function** f from set A to set B is an assignment to each element a in a subset of A, called the domain of definition of f , of a unique element b in B. The sets A and B are called the **domain** and **codomain** of f , respectively. We say that f is undefined for elements in A that are not in the domain of definition of f . When the domain of definition of f equals A, we say that f is a **total function**

### **9.1 Relations and Their Properties**

Let A and B be sets. A **binary relation** from A to B is a subset of A × B.

A **relation** on a set A is a relation from A to A

**[Reflexive]**

(a, a) ∈ R for every element a ∈ A, 

∀a((a, a) ∈ R), where the universe of discourse is the set of all elements in A.

**[Symmetric]**

(b, a) ∈ R whenever(a, b) ∈ R, for all a, b ∈ A

∀a∀b((a, b) ∈ R → (b, a) ∈ R)

**[Antisymmetric]**

For all a, b ∈ A, if (a, b) ∈ R with a ≠ b, then (b, a) not ∈ R

if (a, b) ∈ R and (b, a) ∈ R, then a = b 

∀a∀b(((a, b) ∈ R ∧ (b, a) ∈ R) → (a = b))

**[Transitive]**

(a, b) ∈ R and (b, c) ∈ R, then (a, c) ∈ R, for all a, b, c ∈ A.

∀a∀b∀c(((a, b) ∈ R ∧ (b, c) ∈ R) → (a, c) ∈ R)

**[Composite]**

Let R is A to B and S is B to C. The composite of R and S is the relation consisting of ordered pairs (a, c), where a ∈ A, c ∈ C, and for which there exists an element b ∈ B such that (a, b) ∈ R and (b, c) ∈ S. We denote the composite of R and S by S ◦ R
$$
\begin{align}
&\text{R = {(1, 1), (1, 4), (2, 3), (3, 1), (3, 4)}}\\
&\text{S = {(1, 0), (2, 0), (3, 1), (3, 2), (4, 1)}}\\
&\text{S ◦ R = {(1, 0), (1, 1), (2, 1), (2, 2), (3, 0), (3, 1)}}
\end{align}
$$

### **9.3 Representing Relations**

$$
\text{matrix } M_R = [m_{ij}] 
$$

$$
m_{ij} = 
\left\{\begin{matrix}
 1 & \text{if (}a_i, b_j\text{)} \in R\\ 
 0 & \text{if (}a_i, b_j\text{)} \notin R
\end{matrix}\right.
$$

R is symmetric if and only if $$M_R = (M_R)^t$$

R is antisymmetric relation that $$m_{ij}=0 or m_{ji} = 0 when i \not= j$$ 
$$
M_{R_1 ∪ R_2} = M_{R_1} ∨ M_{R_2}\\
M_{R_1 ∩ R_2} = M_{R_1} ∧ M_{R_2}
$$

$$
M_S ◦ R = M_R \odot  M_S
$$

$$
M_{R^n} = M^{[n]}_R
$$

A **directed graph**, or **digraph**, consists of a set V of **vertices** (or **nodes**) together with a set E of ordered pairs of elements of V called **edges** (or **arcs**). The vertex a is called the **initial vertex** of the edge (a, b), and the vertex b is called the **terminal vertex** of this edge.

Symmetric: every edge we also have the reverse edge

Antisymmetric: which is not a loop, then we don’t have the reverse edge

Transitive: if two consecutive edges, then we also have“combination”

### **9.5 Equivalence Relations**

**[Equivalence]** Reflexive, symmetric, and transitive

**[Equivalent]** Two elements a, b related by equivalence relation, denote a ∼ b 

**[Equivalence Class]**

The set of all elements that are related to an element a of A is called the equivalence class of a. Denoted by [a]R
$$
[a]_R = \{ s | (a, s) ∈ R \}
$$
**[Representative]**

If $$b ∈ [a]_R$$, then b is called a representative of this equivalence class. 

### **9.6 Partial Orderings**

**[Partial ordering]** Reflexive, antisymmetric, and transitive

**[Partially ordered set, Poset]**

Set S with partial ordering R called partially ordered set, or poset, denoted (S, R)

≺= denote relation in any poset, When a and b are elements of the poset (S, ≺=), it is not necessary that either a ≺= b or b ≺= a.

Elements a, b of poset (S, ≺=) called **comparable** if either a ≺= b or b ≺= a. 

a and b are called **incomparable,** neither a ≺= b nor b ≺= a

When every two elements in set are comparable, relation called **total ordering**

If (S, ≺=) is poset and every two elements of S are comparable, S is called a **totally ordered** or **linearly ordered set**, and ≺= is called a **total order** or a **linear order**. A totally ordered set also called **chain**.

(S, ≺=) is **well-ordered set** if it is poset that ≺= is a total ordering and every nonempty subset of S has a least element. 

**[THE PRINCIPLE OF WELL-ORDERED INDUCTION]**

S is a well-ordered set. Then P (x) is true for all x ∈ S, if

**INDUCTIVE STEP:** For every y ∈ S, if P(x) true for all x ∈ S with x ≺ y, then P(y) true

**[Lexicographic Order]**
$$
(a_1, a_2, ..., a_n) ≺ (b_1, b_2, ...,b_n) \text{ if } a_1= b_1 ... a_n = b_n\text{, and } a_{i+1} ≺_{i+1} b_{i+1} 
$$
**[Hasse Diagrams]**

1. Remove all loops since partial ordering is reflexive, a loop (a, a) is present at every vertex a. 
2. Remove all edges (x, y) since there an element z ∈ S such that x ≺ z and z ≺ x
3. Arrange each edge that initial vertex below terminal vertex 
4. Remove all the arrows on the directed edges

Let (S, ≺=) be poset. element y ∈ S **covers** element x ∈ S if x ≺ y and no element z ∈ S that x ≺ z ≺ y. The pairs (x, y) that y covers x called **covering relation** of (S, ≺=)

**[Maximal]** a is maximal in the poset (S, ≺=) if there is no b ∈ S such that a ≺ b

**[Minimal]** a is minimal if there is no element b ∈ S such that b ≺ a

**[Greatest element]** greater than every other element in poset

**[Least element]** less than all other elements in poset

**[Upper bound]**

If u is element of S that a ≺= u for all elements a ∈ A, u is called upper bound of A

**[Lower bound]**

If l is element of S that l ≺= a for all elements a ∈ A, l is called lower bound of A

**[Least upper bound]** Less than every other upper bound

**[Greatest lower bound]** Greater than every other lower bound

**[Lattice]** both a least upper bound and a greatest lower bound

**[Topological Sorting]**

Total ordering ≺= is **compatible** with partial ordering R if a ≺= b whenever aRb. Constructing compatible total ordering from partial ordering called topological sorting

### **5.1 Mathematical Induction**

Prove P(n) is true for all positive integers n, where P (n) is a propositional function

**BASIS STEP:** We verify that P (1) is true. 

**INDUCTIVE STEP:** Show that conditional statement P (k) → P (k + 1) is true for all positive integers k.

Assume that P (k) is true and show under this assumption, P (k + 1) be true

**Example**: Let P(n) be $$1^3 + 2^3 +···+ n^3 = (n(n + 1)/2)^2$$ for positive integer n
$$
P(1): 1 = (1(1+1)/2)^2\\
RHS:(1(1+1)/2)^2=1=LHS
$$
So P(1) is true

Assume that P(k) is true, 
$$
1^3 + 2^3 + ... + k^3 = (k(k+1)/2)^2
$$
Note that P(k+1) is 
$$
1^3 + 2^3 + ... + k^3+ (k+1)^3 = ((k+1)(k+2)/2)^2
$$
and then
$$
\begin{align}
1^3 + 2^3 + ... + k^3 + (k+1)^3 &= (k(k+1)/2)^2 + (k+1)^3 \\
&= k^2(k+1)^2/4 + (k+1)^3\\
&= (k+1)^2(k^2/4 + (k+1))\\
&=  (k+1)^2(k+2)^2/4\\
&=  ((k+1)(k+2)/2)^2\\
&= P(k+1)
\end{align}
$$
It shows P(k+1) is true when P(k) is true

By mathematical induction, P(n) is true for all positive integers n

### **5.3 Recursive Definitions and Structural Induction**

Define function with set of nonnegative integers domain: 

**BASIS STEP:** Specify value of function at zero

**RECURSIVE STEP:** Give a rule for finding its value at an integer from its values at smaller integers

It is called **recursive** or **inductive definition**

**[Arithmetic sequence]** 
$$
a_n = a_{n-1} + d\\
a_n = a_0 + nd
$$
**[Geometric sequence]** 
$$
a_n = ca_n-1 \\
a_n = c^n a_0
$$
**[Compound interest]**
$$
P_n = r^n P_0
$$

### **8.2 Solving Linear Recurrence Relations**

**Linear homogeneous recurrence relation of degree k with constant coefficients**
$$
a_n = c_1a_{n-1} + c_2a_{n-2} + . . . + c_k a_{n-k}
$$
where $$c_1, c_2, . . . , c_k$$ are real numbers with $$c_k \not= 0$$

**[Linear]**  $$a_k$$ power by 1

**[Homogeneous]**  all arguments multiple by some $$a_k$$

**[Degree k]** $$a_n$$ depends on the kth preceding term

**[Constant coefficients]** all coefficients are constants

**[Characteristic equation]**
$$
r^k-c_1r^{k-1}-c_2r^{k-2}-...- c_{k-1}r-c_k=0
$$
**[Characteristic roots]** roots of characteristic equation

Solution of degree two:
$$
a_n = c_1 a_{n-1} + c_2 a_{n-2}\\
r^2 -c_1 r - c_2 = 0 \text{, we have } r_1, r_2 (r_1 \not= r_2)\\
a_n = a_1 r^n_1 + a_2 r^n_2
$$
Solution of degree two with same r root:
$$
r^2 - c_1 r - c_2 = 0 \text{, we have } r_0\\
a_n = a_1 r^n_0 + a_2 n r^n_0
$$
Solution of degree k with distinct r roots:
$$
a_n = c_1a_{n-1} + c_2a_{n-2} + . . . + c_k a_{n-k}\\
r^k-c_1r^{k-1}-...-c_k=0 \text{, we have }r_1, r_2, ..., r_k \text{(distinct roots)}\\
a_n=a_1r_1^n+a_nr_2^n+...+a_kr_k^n
$$
General solution of linear homogeneous recurrence relations with constant coefficients:
$$
r^k-c_1r^{k-1}-...-c_k=0 \text{, we have t distinct roots} \\\\
\text{the root multiply by } m_1, m_2, ..., m_t \text{ times}\\\\
m_1+m_2+...+m_t=k\\\\
\begin{align}
a_n=&(a_{1,0}+a_{1,1}n+...+a_{1,m_1-1}n^{m_1-1})r_1^n+\\
&(a_{2,0}+a_{2,1}n+...+a_{2,m_2-1}n^{m_2-1})r_2^n+\\
   &     + ... + (a_{t,0}+a_{t,1}n+...+a_{t,m_t-1}n^{m_t-1})r_t^n
        \end{align}\\
\text{where }a_{i,j} \text{ are }1 \leq  i\leq t \text{ and }0\leq j\leq m_j-1\\
a_n= \sum_{i=0}^t(\sum_{j=0}^{m_t-1}a_{i,j}n^j)r_t^n
$$
Nonhomogeneous linear recurrence relation with constant coefficients
$$
a_n = c_1a_{n-1} + c_2a_{n-2} + . . . + c_k a_{n-k} + F(n)
$$
$$a_n^{(p)}$$is a particular solution of the nonhomogeneous linear recurrence relation with constant coefficients

$$a_n^{(h)}$$is a solution of the associated homogeneous recurrence relation
$$
a_n=a_n^{(p)}+a_n^{(h)}
$$
Format of F(n):
$$
F(n) = (b_tn^t+b_{t-1}n^{t-1} + ... + b_1 n + b_0)s^n
$$
When s is not a root of the characteristic equation of the associated linear homogeneous recurrence relation, there is a particular solution of the form
$$
a^{(p)}_n=(p_t n^t + p_{t-1}n^{t-1}+...+p_1n+p_0)s^n
$$
When s is a root of this characteristic equation and its multiplicity is m, there is a particular solution of the form
$$
a^{(p)}_n= n^m(p_t n^t + p_{t-1}n^{t-1}+...+p_1n+p_0)s^n
$$

### **6.1 The Basics of Counting**

$$A_k$$ is set of ways

There are $$n_1, n_2, ..., n_k$$, n is number of ways, k is number of task

**[Product rule]** 
$$
| A_1 × A_2 × ... × A_k | = |A_1| |A_2| ... |A_k| = n_1 n_2 ... n_k
$$
**[Sum rule]**
$$
| A_1 ∪ A_2 ∪ ... ∪ A_k | = |A_1| +|A_2| + ... + |A_k| = n_1 + n_2 + ... + n_k
$$
**[Subtraction Rule]** 
$$
| A_1 ∪ A_2 | = |A_1| + |A_2| - |A_1 ∩ A_2 |
$$
**[Division Rule]** If finite set A is the union of n pairwise disjoint subsets each with d elements, then n = |A| / d

Counting problems can solved by **tree diagrams**

**[Pigeonhole principle]**

Assume that

**pigeons**: n + 1 objects are placed into

**pigeonholes**: n boxes

At least one box contains two or more objects

### **6.3 Permutations and Combinations**

$$
P(n, r) = \frac{n!}{(n-r)!}\\
C(n, r) = \frac{n!}{r!(n-r)!}\\
\binom{n}{r} = \binom{n}{n-r}
$$

### **6.4 Binomial Coefficients and Identities**

$$
(x + y)^n = \sum^n_{k=0} \binom{n}{k} x^{n-k}y^k\\
 \sum^n_{k=0} \binom{n}{k} = 2^n\\
  \sum^n_{j=0}(-1)^j \binom{n}{j} = 0\\
  \binom{n}{k} = \binom{n-1}{k} + \binom{n-1}{k-1}
$$

