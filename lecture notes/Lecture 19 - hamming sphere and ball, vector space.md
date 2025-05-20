# Lecture 19: Hamming Sphere and Ball, Vector Space

**Summary:**
We explore Hamming spheres and balls, establishing formulas for their sizes and examining their role in error correction. We prove bounds on code size based on error-correcting capabilities and introduce vector spaces, defining their fundamental properties and operations. We demonstrate how these concepts provide a framework for understanding linear codes.

**Topics Covered:** Hamming ball, Hamming sphere, vector space

**Proposition:**

$C$ is a code with Hamming distance $d(C)$
1. $C$ detects up to $s$ errors $\iff$ $d(C) \geq s + 1$
2. $C$ corrects up to $t$ errors $\iff$ $d(C) \geq 2t + 1$

**Hamming sphere:**

$$x \in \mathbb{F}_q ^ m, r \in \mathbb{N}$$
The Hamming sphere with center $x$ and radius $r$ is denoted
$$S(x, r) = \{y \in \mathbb{F}_q ^ m \space : \space d(x, y) = r\}$$
**Hamming ball:**
$$B(x, r) = \{y \in \mathbb{F}_q ^ m \space : \space d(x, y) \leq r\}$$
Note that
$$|\mathbb{F}_q ^ m| = q ^ m$$

**Example 1:**

$$x = (1, 1) \in \mathbb{F}_2 ^ 2, \space r = 1$$
$$S(x, r) = \{(0, 1), (1, 0)\}$$
$$B(x, r) = \{(1, 1), (0, 1), (1, 0)\}$$

Suppose we have $r = 2$. Then, we get
$$S(x, r) = \{(0, 0)\}$$
$$B(x, r) = \mathbb{F}_2 ^ 2$$
**Example 2:**
$$x = (a, b, c, d) \in \mathbb{F}_q ^ 4, \space r = 2$$

**Lemma:**

$$|S(x, r)| = \binom{m}{r}(q - 1)^r$$
$$|B(x, r)| = \sum_{i = 0} ^ r\binom{m}{r}(q - 1) ^ i$$
Note that
$$B(x, r) = \bigsqcup_{i = 0} ^ r S(x, i)$$

**Binomial theorem:**

![[binomial theorem]]

**Theorem:**

Let $C \subseteq \mathbb{F} _ q ^ m$ be a code of size $M = |C|$.

Suppose that $C$ corrects up to $t$ errors.

Then,
$$M \sum_{i = 0} ^ t \binom{m}{i}(q - 1) ^ i \leq q ^ m$$
$$M \leq \frac{q ^ m}{\sum_{i = 0} ^ t \binom{m}{i}(q - 1) ^ i}$$
**Proof:**

Since $C$ corrects up to $t$ errors, we know that $d(C) \geq 2t + 1$.

$$\implies y_1, y_2 \in C, \space y_1 \neq y_2, \space d(y_1, y_2) \geq 2t + 1 \implies$$
$$B(y, t) \cap B(y_2, t) = \emptyset$$

$$a \in B(y_1, t) \cap B(y_2, t)$$

$$d(y_1, y_2) \subseteq d(y-1, a) + d(a, y_2) \leq 2t$$

Note that
$$|\mathbb{F}_q ^ m| = q ^ m$$
points

For each of the $M$ elements of $C$, we have a ball of radius $t$ around it with
$$\sum_{i = 1} ^ t \binom{m}{i}(q - 1) ^ i \leq q ^ m$$
**Example:**

$C \subseteq \mathbb{F}_2 ^ {10}$ code that corrects up to $2$ errors. Show that $|C| \leq 18$.

*Solution:*

$$|C| \left ( \sum_{i = 0} ^ 2 \binom{10}{i} \right ) \leq 2 ^ {10}$$
$$\binom{10}{0} + \binom{10}{1} + \binom{10}{2}$$
$$|C| \leq \frac{1024}{56} = 18.3$$
**Definition:**

A vector space is a set $\mathcal{V}$ over a field $\mathbb{F}$ with a binary operation $+$ on $\mathcal{V}$ and a scalar multiplication operation $\cdot : \space \mathbb{F} \times \mathcal{V} \rightarrow \mathcal{V}$ such that

1. $\forall u, v \in \mathcal{V} . \space u + v \in \mathcal{V}$
2. $\forall u, v, w \in\mathcal{V} . \space (u + v) + w = u + (v + w)$
3. $\exists \vec{0} \in \mathcal{V} . \space \forall v \in \mathcal{V} . \space \vec{0} + v = v$
4. $\forall v \in \mathcal{V} . \space \exists (-v) \in \mathcal{V} . \space v + (-v) = \vec{0}$
5. $\forall u, v \in \mathcal{V} . \space. u + v = v + u$
6. $\forall a \in \mathbb{F} . \forall v \in \mathcal{V} . \space \space av \in \mathcal{V}$
7. $\forall a, b \in \mathbb{F} . \space \forall v \in \mathcal{V} . \space a(bv) = (ab)v$
8. $\forall a, b \in \mathbb{F} . \space \forall v \in \mathcal{V} . \space (a + b) \cdot v = av + bv$
9. $\forall a \in \mathbb{F}. \space \forall u, v \in \mathcal{V} . \space a(u + v) = au + av$
10. $\forall v \in \mathcal{V} . \space 1 \cdot v = v$
