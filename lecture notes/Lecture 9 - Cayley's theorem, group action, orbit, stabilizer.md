# Lecture 9: Cayley's Theorem, Group Action, Orbit, Stabilizer

**Summary:**
We prove Cayley's theorem, which states that every group is isomorphic to a permutation group. We introduce group actions and show how they provide a way for groups to act on sets. We define orbits and stabilizers, proving that orbits partition the set and that stabilizers are subgroups. We demonstrate how group actions can be used to study symmetries, using the example of a necklace with beads. We prove that the size of an orbit times the size of its stabilizer equals the order of the group, when the group is finite.

**Topics Covered:** Cayley's theorem, group action, orbit, stabilizer

**Definition:**

A subgroup of the symmetric group $\text{Sym}(S)$ on a set $S$ is called a permutation group.

**Example:**
$$S_3 \supseteq \langle (1, 2, 3) \rangle$$
**Theorem (Cayley):**

Every group is isomorphic to a permutation group.

**Proof:**

Let $G$ be an arbitrary group. We want an isomorphism from $G$ to some permutation group.

$$\phi : G \rightarrow \text{Sym}(G)$$
$$a \mapsto \lambda _ a \in \text{Sym}(G)$$

Note that $\lambda _ a : G \rightarrow G$ is a bijection, due to the invertibility of $a \in G$.

Given any $x \in G$, we need to define $\lambda_a(x)$.

Define $\lambda_a : G \rightarrow G$ as
$$\lambda_a (x) = a \cdot x$$
Note that $\lambda_a$ is a bijection
- $\lambda_a$ is an injection because
	- $a x_1 = a x_2 \implies x_1 = x_2$ (cancellation lemma)
- $\lambda_a$ is a surjection because
	- $\forall b \in G . \space ax = b \iff x = a ^ {-1} b$

Let
$$G _ \lambda = \phi(G) \subseteq \text{Sym}(G)$$
We want to verify that
1. $G _ \lambda$ is a subgroup of $G$
2. $\phi : G \rightarrow G _ \lambda$ as defined above is a group isomorphism

Want $G _ \lambda$ to be a subgroup of $\text{Sym}(G)$
$$e \in G$$
$$\lambda_e : G \rightarrow G$$
$$g \mapsto g$$

Therefore, $\lambda _ e \in G _ \lambda$ is the identity

- We also need $\lambda_a \lambda_b = \lambda _ {ab}$
	- $a(bx) = (ab)x \implies \forall \lambda _ a, \lambda _b  \implies \lambda _a \lambda _ b \in G _ \lambda$
$$\left ( \lambda _ a \right ) ^ {-1} = \lambda _ {a ^ {-1}}$$

# Group actions

Suppose we have a necklace with 9 beads. We want to describe the permutations of the necklace as a group.

We can generate the group as follows:
$$\left \langle \begin{pmatrix}
1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 \\
2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 1
\end{pmatrix}
\right \rangle$$
**Definition:**

Let $G$ be a group with identity $e$, and let $X$ be a set. We say that $G$ acts on $X$ if $\forall g \in G$ there exists a map $g : X \rightarrow X$ such that $\forall x \in X$
1. $\forall h, g \in G . \space h(g(x)) = (hg)(x)$
2. $e(x) = x$

**Lemma:** In the above setup, $\forall g \in G$ the map $g : X \rightarrow X$ is a bijection.

**Proof:**

To prove that $g$ is a bijection, it suffices to show that it has an inverse.

**Example:**

$$(1, 2, 3, 4) \in S_4$$
$$G = \left \langle (1, 2, 3, 4)\right \rangle = \{e, (1, 2, 3, 4), (1, 3)(2, 4), (1, 4, 3, 2)\}$$
$G$ acts on $[4]$.
$$X = \{\{1, 2 \}, \{1, 3 \}, \{1, 4\}, \{2, 3\}, \{2, 4\}, \{3, 4\}$$

We claim that $g ^ {-1} : X \rightarrow X$
$$g ^ {-1}(g(x)) = (g ^ {-1} g)(x) = e(x) = x$$
and
$$g(g ^ {-1}(x)) = g ^ {-1}(g(x))$$


**Definition:**

If $G$ acts on $X$, then the orbit of $x \in X$ is
$$\mathcal{O}_x = \{g (x) \space : \space g \in G \} \subseteq X$$


$$\mathcal{O} _ {\{1, 2\}} = \left \{ e \space \{1, 2 \}, (1, 2, 3, 4) \space \{1, 2\}, \right (1, 3)(2 4) \space \{1, 2\}, (1, 4, 3, 2) \space \{1, 2\}\}$$

Note that
$$X = \mathcal{O} _ {\{1, 2\}} \sqcup \mathcal{O} _ {\{1, 3\}}$$
**Definition:**

If $G$ acts on $X$, then the stabilizer of $x \in X$ is
$$G _ x  = \{g \in G \space : \space gx = x \} \subseteq G$$
Note that the stabilizer $G_x$ is a subgroup of $G$.

