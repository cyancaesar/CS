# Lecture One - Introduction

**Properties of Algorithms**

- Ordered sequence of precise steps
- Finite number of instructions
- Not ambiguous
- Correct - (Semantically and Syntactically)
- Terminate

**Major Factors in Algorithms Design**

- Correctness
- Algorithm Efficiency

**Designing Techniques**

- Brute Force
- Divide-and-Conquer
- Iterative Improvement
- Decrease-and-Conquer
- Transform-and-Conquer
- Dynamic Programming

**Two Essential Approaches to Measuring Algorithm Efficiency**

- Empirical analysis
- Theoretical analysis

**Three Cases of Algorithm Analysis**

- Word case - *upper bound*
- Average case
- Best case - *lower bound*

**Complexity of Algorithm**

Defined as the amount of work the algorithm performs to complete its task, overall measured by:
- Time complexity
- Computational complexity
- Space complexity

---

# Lecture Two - Asymptotic Analysis

**Asymptotic Analysis**

Determines the running time in big-Oh notation.

**Important Functions**

| Function |    Name     |
| :------: | :---------: |
|    c     |  Constant   |
|  log N   | Logarithmic |
| log^2 N  | Log-squared |
|    N     |   Linear    |
| N log N  |   N log N   |
|   N^2    |  Quadratic  |
|   N^3    |    Cubic    |
|   2^N    | Exponential |

**Asymptotic Notation**

- O notation: *less than*
	- `f(n) = O(g(n))` implies: `f(n) <= g(n)`
- Ω notation: *greater than*
	- `f(n) = Ω(g(n))` implies: `f(n) >= g(n)`
- Θ notation: *equality*
	- `f(n) = Θ(g(n))` implies: `f(n) = g(n)`

**Find $n_0$ and $c$**

$1000n^2+1000n=O(n^2)$

---

# Lecture Three - Recurrence

---

# Lecture Four - Sorting

---

# Lecture Five  - Binary Search

**Successor**

`successor(x) = y`, such that `key[y]` is the smallest `key > key[x]`.

- Case one: `right(x)` is non empty
	- The minimum in `right(x)`
- Case two: `right(x)` is empty
	- Go up the tree until the current node has a left child
	- If no left, root is the largest element

**Predecessor**

`predecessor(x) = y`, such that `key[y]` is the biggest `key < key[x]`

- Case one: `left(x)` is non empty
	- The maximum in `left(x)`
- Case two: `left(x)` is empty
	- Go up the tree until the current node has a right child
	- If no right, root is the smallest

---

# Lecture 5.1

- Count sort: `O(n)`
- Radix sort: `O(d(n+k))`

---

# Lecture 6 - Graph

- Directed graph: `|E|`
- Undirected graph: `2|E|`
- Memory: `O(V+E)`
- Adjacency list: **Sparse** when `|E| << |V|^2`
- Adjacency matrix: **Dense** when `|E| close to |V|^2`
- BFS and DFS

---

# Lecture 7 - NP

**Class P**

- Solvable in polynomial-time algorithms

Problems in **P** are *tractable*, otherwise they're *interactable/unsolvable*.

**Interactable Problems**

- Hamiltonian Paths
- Traveling Salesman

**Interactable Problems Classification**

- NP
- NP-complete
- NP-hard

**Nondeterministic algorithm** - two stage

1. Nondeterministic stage
2. Deterministic stage

**Class NP**

- Could be solved by NP algorithms

**NP-complete**

- The hardest in NP

**P & NP-complete Problems**

- Shortest simple path
	- P
- Longest simple path
	- NP-complete
- Euler tour
	- P
- Hamiltonian cycle
	- NP-complete

