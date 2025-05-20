# Lecture 10: Group Action, Burnside's Lemma

**Summary:**
We continue our study of group actions and apply them to counting problems. We prove that orbits partition the set and that stabilizers are subgroups. We introduce fixed points and prove Burnside's lemma, which provides a formula for counting the number of distinct orbits in a group action. We demonstrate how to use Burnside's lemma to solve counting problems involving symmetries, such as counting distinct colorings of objects under rotational symmetry.

**Topics Covered:** Burnside's lemma, coset, fixed point set, group action, group action orbit, group action stabilizer

**Group action:**

Let $G$ be a group with $e \in G$ identity. Let $X$ be a set. We say that group $G$ acts on $X$ when $\forall g \in G$ we have a map $g : X \rightarrow X$ such that $\forall x \in X$
1. $h(g(x)) = (hg)(x)$
2. $e(x) = x$

Note that we use $g$ to denote both the group element $g \in G$ and the corresponding function $g : X \rightarrow X$.

Permutation groups (subgroups of $S_n$) naturally act on the numbers $[n] = \{1, 2, ...., n\}$ in the obvious way; by mapping each number to its image under the permutation. For example,
$$G = \langle (1, 4, 3, 2) \rangle = \langle (1, 2, 3, 4) \rangle \leq S_4$$


For example
$$\langle (1, 4, 3, 2) \rangle = \langle (1, 2, 3, 4) \rangle \subseteq S_4$$
$$X = \{\{1, 2\}, \{1, 3\}, \{1, 4\}, \{2, 3\}, \{2, 4\}, \{3, 4\}\}$$
We define
$$g \{a, b\} = \{g a, g b\}$$

**Orbit:**

Let $x \in X$. Then, we have
$$\mathcal{O}_x = \{ g(x) \in X \space : \space g \in G\}$$

**Stabilizer:**
$$G _ x = \{g \in G \space : \space g (x) = x\}$$
$$\mathcal{O}_{\{1, 2\}} = \{e \{1, 2\}, (1, 2, 3, 4) \{1, 2\}, (1, 3) \{1, 2\}, (1, 4, 3, 2) \{1,2\}\}$$
$$= \{\{1, 2\}, \{2, 3\} ,\{3, 4\}, \{4, 1\}\}
$$
We notice that
$$|\mathcal{O} _ {\{1, 2\}}| \cdot |G _ {\{1, 2\}}| = |\mathcal{O} _ {\{1, 3\}}| \cdot |G _ {\{1, 3\}}| = |G|$$
**Lemma 1:**

Let $G$ act on $X$
1. The distinct orbits partition $X$
2. Let $x \in X$. Then, $G_x$ is a subgroup of $G$
3. If $G$ and $X$ are finite, then for $x \in X$, we have $|\mathcal{O}_x| \cdot |G _ x| = |G|$

**Proof of 1:**

Let $\mathcal{O} ^ {(1)}, .... \mathcal{O} ^ {(k)}$ be all the distinct orbits.

Note that by definition,
$$\mathcal{O} ^ {(i)} \subseteq X \implies \bigcup _ {i = 1} ^ k \mathcal{O} ^ {(i)} \subseteq X$$
Moreover, $\forall x \in X$,
$$x \in \mathcal{O} _x \implies X \subseteq \bigcup _{i = 1} ^ k \mathcal{O} ^ {(i)}$$
$$\implies X = \bigcup_{i = 1} ^ k \mathcal{O} ^ {(i)}$$
To show that the orbits partition, we must show that $\mathcal{O} ^ {(1)}, ...., \mathcal{O} ^ {(k)}$ are disjoint. Equivalently, we will show that
$$\mathcal{O} _ x \cap \mathcal{O} _ y \neq \emptyset \implies \mathcal{O}_x = \mathcal{O}_y$$
We'll show that $\mathcal{O} _ x \subseteq \mathcal{O} _y$, and the containment $\mathcal{O} _ y \subseteq \mathcal{O}_x$ is similar.

$$z \in \mathcal{O} _ x \implies \exists g \in G . \space g(x) = z$$
$$u \in \mathcal{O} _ x \cap \mathcal{O} _ y \implies \exists h, k \in G. \space u = hx \space \text{and} \space u = ky$$

**Claim:**
$$u = hx \iff x = h ^ {-1} u$$
$$x = ex = (h ^ {-1} h) (x) = h ^ {-1}(h(x)) = h ^ {-1}(u)$$
$$z = gx = g (h ^ {-1}u) = g ( h ^ {_1} ky) = (g h ^ {-1}k) y \in \mathcal{O} _ y$$

**Proof of 2:**

We want to show that $\forall x \in X . \space$ $G_x$ is a subgroup of $G$.

Note that $e \in G_x$ because $e(x) = e$. So, $e$ is in the stabilizer of $x$.

We know that
$$g \in G_x \iff gx = x$$
Note that
$$g x = x \iff g ^ {-1} x = x$$
Therefore, $G_x$ is closed under inverses.

Now, we want to show that
$$\forall g, h \in G_x . \space gh \in G_x$$
Let $g, h \in G_x$. Then,$$(gh)(x) = g(h(x)) = g(x) = x$$

$$\implies (gh) = x$$
$$\implies gh \in G_x$$
Therefore, $G_x$ is closed under multiplication (composition).

Therefore, $G_x$ is a subgroup of $G$.
$$QED$$

**Theorem (Lagrange):**

Let $G$ be a finite group and $H$ be a subgroup of $G$. Then, we have that $|H|$ divides $|G|$.

Idea: For each $a \in G$, we have
$$H a = \{h a \space : \space h \in H\}$$
$$|H a| = |H|$$
The $Ha$s partition $H$

Equivalently, we have
$$aH = \{a h \space : \space h \in H \}$$
$$|aH| = |H|$$

The $aH$s also partition $H$.

This is the start to the proof of Lagrange's theorem.

$G$: the left cosets of $G_x$ partition $G$ (as we've written the proof of Lagrange's theorem)

3 claims that the number of distinct left cosets is $\mathcal{O} _ x$

$$\mathcal{O} _ {\{1, 3\}} = \{\{1, 3\}, \{2, 4\}\}$$
$$G _ {\{1, 3\}} = \{e, (1, 3), (2, 4)\} = e G _ {\{1, 3\}}$$

$$G = \langle (1, 2, 3, 4) \rangle$$
$$(1, 2, 3, 4) G _ {\{1, 3\}} = \{(1, 2, 3, 4), (1, 4, 3 ,2)\}$$

We will find a bijection
$$f : \{a G _ x \space : \space a \in G\} \rightarrow \mathcal{O}_x$$
The left side of the function is the set of left cosets of $\mathcal{O}_x$

$$f \left ( g G_x \right ) = gx \in \mathcal{O}_x$$

We want to show that this function is well-defined, which means
$$g G_x = hG _x \implies gx = hx$$

> Fill this in later

We will show that $f$ is a bijection by showing that it is invertible.
$$f ^ {-1} : \mathcal{O}_x \rightarrow \{a G_x \space : \space a \in G\}$$
$$gx \mapsto gG_x$$
We need to show that $f ^ {-1}$ is well-defined, which we show by verifying
$$gx = hx \implies g G_x = hG_x$$

Suppose that $gx = hx$. Then,
$$\implies x = \left ( g ^ {-1}h \right ) x$$
$$\implies g ^ {-1} h \in G_x$$
$$\iff gG_x = hG_x$$
$$QED$$

**Definition:**

If $G$ acts on $X$, then the fixed point set of $g \in G$ is
$$X ^ g = \{x \in X \space : \space gx = x\} \subseteq X$$

**Example:**
$$X ^ {(1, 3)} = X ^ {(2, 4)} = \{\{1, 3\}, \{2, 4\}\}$$
**Burnside's lemma:**

Let $G$ act on $X$ with $G, X$ finite.

Then,
$$\text{number of orbits of a group action} = \frac{1}{|G|} \sum_{g \in G} |X ^ g|$$
