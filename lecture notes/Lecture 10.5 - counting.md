# Lecture 10.5: Counting

**Summary:**
We study fundamental counting principles, permutations, and subsets. We establish that n elements have n! permutations and 2^n subsets, and introduce binomial coefficients and the binomial theorem.

**Topics Covered:** addition principle, binomial coefficient, binomial theorem, counting subset, multiplication principle, permutation

# Two basic counting principles

- Multiplication principle
	- If there are $a$ ways of performing task A and $b$ ways of performing task B, then, there are $ab$ ways of performing A then B.
- Addition principle
	- If there are $a$ ways of performing task A and $b$ ways of performing task B, then, there are $a + b$ ways of performing A or B

# Permutations

$$S_n = \{\text{permutations of} \space [n]\}$$
$$|S_n| = n!$$

# Subsets

$$2 ^ S = \{\text{Subsets of } S\}$$
Note that
$$|2 ^ S| = 2 ^ {|S|}$$

Note that there is a bijection
$$2 ^ S \rightarrow \{0, 1\} ^ {|S|}$$


# Binomial coefficient

$$\binom{n}{k} := \frac{n!}{k!(n - k)!}$$

$\binom{n}{k}$ is the number of ways we can pick a $k$-subset from a set of size $n$.

# Generating functions

The multivariate generating function for subsets of $[n]$ is
$$\sum_{A \subseteq [n]} \prod _{i \in A}x_i = (1 + x_1)(1 + x_2) ....(1 + x_n)$$

Plug in $x_1 = x_2 = .... = x_n= x$ to get

$$\sum_{A \subseteq [n]} x ^ {|A|} = (1 + x) ^ n$$
**Binomial theorem:**
$$\sum_{i = 0} ^ n \binom{n}{k} x ^ k = (1 + x) ^ n$$
