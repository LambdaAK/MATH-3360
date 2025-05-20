# Lecture 1: Functions and Their Properties

**Summary:**
This lecture introduces the fundamental concept of functions and their key properties. We explore three essential types of functions:
- Injective (one-to-one) functions, where each element in the codomain has at most one pre-image
- Surjective (onto) functions, where each element in the codomain has at least one pre-image
- Bijective functions, which are both injective and surjective

**Topics Covered:** function, set, Identity function, inverse function, injectivity, surjectivity, bijectivity, cardinality, image, rationals, function composition

We also examine important properties of functions, including:
- Function composition and its properties
- The identity function and its role
- Inverse functions and their relationship to bijective functions
- The conditions under which a function has an inverse

These concepts form the foundation for understanding more complex mathematical structures and transformations that will be explored in later lectures.

# Cardinality

- The cardinality of a (finite) set $A$, denoted $|A|$ or $\#A$ is the numbenr of elements in the set.

Note that
$$|A \times B| = |A| \cdot |B|$$
# Functions

$$f : \mathbb{R} \rightarrow \mathbb{R}$$
$$f(x) = x ^ 2$$
The graph of the function is
$$\{(x, y) \in \mathbb{R} ^ 2 : \space y = f(x)\}$$
Cartesian product
$$A \times B = \{(a, b) : a \in A , b \in B\}$$
Note that
$$|A \times B | = |A| \cdot |B|$$
$|A|$ is the number of elements in a set

**Definition - function:** Let $S$ and $T$ be two sets. A function from $S$ to $T$ is a subset $F \subseteq S \times T$ such that $\forall x \in S . \space \exists y \in T . \space (x, y) \in F$.

$S$ is called the domain of $F$

$T$ is the codomain, or range of $F$

$$(x, y) \in F \iff f(x) = y$$
**Example:**

$$f : \mathbb{Q} \rightarrow \mathbb{Z}$$
$$f \left ( \frac{m}{n} \right ) = m$$
Note that this is not a function because a rational number can have multiple representations
$$f \left ( \frac{1}{3} \right ) = 1, \space f \left ( \frac{2}{6} \right ) = 2$$
And $\frac{1}{3} = \frac{2}{6}$, so, it is not the case that for any $r \in \mathbb{Q} . \space \exists ! y \in \mathbb{Z} . \space f(r) = y$.

**Definition:** Let $A \subseteq S$. The **inclusion function** $\iota : A \rightarrow S$ is such that $\forall a \in A . \space \iota(a) = a$.

**Definition:** Let $f : S \rightarrow T$ and $g : T \rightarrow U$ be two functions. We define the composition
$$(g \circ f)(x) = g(f(x))$$

> Try writing the composition of functions in cartesian product language.

**Proposition:** Let $f : S \rightarrow T, g : T \rightarrow U, R : U \rightarrow V$. Then,
$$h \circ (g \circ f) = (h \circ g) \circ f$$
In other words, function composition is associative.

This is easy to prove using the definition of composition.

**Definition:** The function $f : S \rightarrow T$ is **onto** means $\text{im}(f) = T$. In other words, $\forall t \in T . \space \exists s \in S . \space f(s) = t$. This is also called a **surjection**.

**Definition:** The function $f : S \rightarrow T$ is **one-to-one** means $f(x_1) = f(x_2) \implies x_1 = x_2$. This is also called an injection.

**Definition:** The function $f : S \rightarrow T$ is a **one-to-one correspondence** means $f$ is injective and surjective. This is also called a bijection.

**Example:**
$$f : \{1, 2 \} \rightarrow \{3, 4, 5 \}$$
Note that $f$ cannot be a surjection.

$f$ can be an injection, for example:
$$1 \rightarrow 3$$
$$3 \rightarrow 5$$

Consider the bijection
$$g : \{1, 2, 3 \} \rightarrow \{3, 4, 5\}$$
$$1 \rightarrow 4$$
$$3 \rightarrow 3$$
$$2 \rightarrow 5$$
Note that on the left, each elements appears exactly once, and same on the right side.

**Identity function:**
$$1 _ S : S \rightarrow S$$
$$\forall x \in S . \space 1_S(x) = x$$
Note that for any function $f$, we have
$$1_S \circ f = f \circ 1_S = f$$
**Inverse function:**

Let $f : S \rightarrow T$ and let $g : T \rightarrow S$ be functions. The functions $f$ and $g$ are inverses of each other means
$$f \circ g = 1 _ T$$
$$g \circ f = 1_S$$

**Proposition:** If $f$ has an inverse, then the inverse is unique.

**Proof:**

Suppose that $g, h : T \rightarrow S$ are inverses of $f$.

We want to show that $g = h$.

Note that
$$\underbrace{(h \circ f)} _ {1 _ S} \circ g = h \circ \underbrace{(f \circ g)}_{1_T}$$
$$\implies 1_S \circ g = h \circ 1 _ T$$
$$\implies g = h$$
$$QED$$
**Proposition:** $f : S \rightarrow T, g : T \rightarrow U$. Then,
1. $f$ and $g$ are onto $\implies g \circ f$ is onto
2. $f$ and $g$ are one-to-one $\implies$ $g \circ f$ one-to-one

**Proof of 1:**

$\forall z \in U . \space \exists t \in T . \space g(t) = u$, since $g$ is onto.

$\forall t \in T . \space \exists s \in S . \space f(s) = t$, since $f$ is onto

Therefore,

$$(g \circ f)s(s) = g(f(s)) = u \implies g \circ f \space \text{is onto}$$
$$QED$$

**Proof of 2:**

$$g(f(x_1)) = g(f(x_2) , \space x_1, x_2 \in S$$
Since $g$ is one-to-one $\implies$ $f(x_1) = f(x_2)$

$$x_1 = x_2$$
$$QED$$
**Corollary:** If $f, g$ are bijections $\implies$ $g \circ f$ is a bijection.

**Proposition:** Let $f : S \rightarrow T$ be a function.

$f$ has an inverse $\iff$ $f$ is bijective.

**$\implies$ proof:**

Suppose that $f$ has an inverse $g : T \rightarrow S$ such that
$$g \circ f = 1 _ S, \space f \circ g = 1_T$$
Let $y \in T$. Note that
$$y = 1_T(y) = (f \circ g)(y) = f(g(y))$$
$$\forall y \in T . \space f : g(y) \rightarrow y$$
So, $f$ is onto

Let $x_1, x_2 \in S$ and suppose
$$f(x_1) = f(x_2)$$
$$\implies g(f(x_1)) = g(f(x_2))$$
$$\implies (g \circ f)(x_1) = (g \circ f)(x_2)$$
$$\implies x_1 = x_2$$
Since $(g \circ f)$ is the identity function
$$QED$$

**$\impliedby$ proof:**

Suppose that $f$ is a bijection. We want to show that $g$ has an inverse.

Define $g : T \rightarrow S$ as follows
$$\forall y \in T . \space \exists x \in S . \space f(x) = y$$
Define $g(y) = x$.

We propose that $g$ is the inverse of $f$.

We must check that
$$f \circ g = 1_T$$
$$g \circ f = 1_S$$

