## Probability and Statistics

07 Jan 2022

---

### Concept of a Random Variable

It's all about assigning numerical values to the outcomes

<span style='color:pink'>Example</span>

Testing two components:
- D : Defective
- N : Non-Defective
- Sample Space = `{DD, DN, ND, NN}`

$\text{Let } X = \text{number of defective components when two components are tested}$

| Outcomes | Numerical Value $X$ |
|:--------:|:-------------------:|
|    DD    |          2          |
|    DN    |          1          |
|    ND    |          1          |
|    NN    |          0          |

The set of all possible values of the random variable $X$ is $\{0,1,2\}$

<span style='color:red'>Definition</span>
A random variable $X$ is a function that associates each element in the sample space with a real number $\{X: S\to R\}$

<span style='color:lightgreen'>Notation</span>
$X$ denotes the random variable.
$x$ denotes a value of the random variable $X$.

<span style='color:lightgreen'>Types of Random Variables</span>

**Discrete**
If the set of possible values is countable
$x \in \{x_1, x_2,...,x_n\}$

**Continuous**
Random variable $X$ is continuous if it can take values on a continuous scale (interval)
$x \in \{x:a<x<b\}$

---

<span style='color:red'>Discrete Probability Distributions</span>

A discrete random variable $X$ assumes each of its values with a certain probability; called **Mass Function**.

<span style='color:pink'>Example</span>

Experiment: tossing a non-balance coin 2 times independently
- Sample Space: $S=\{HH,HT,TH,HH\}$
- Suppose $P(H)=\frac{1}{3}$ and $P(T)=\frac{2}{3}$

| Outcome |  Probability  | Value of $X$ |
|:-------:|:-------------:|:------------:|
|   HH    | $\frac{1}{9}$ |      2       |
|   HT    | $\frac{2}{9}$ |      1       |
|   TH    | $\frac{2}{9}$ |      1       |
|   TT    | $\frac{4}{9}$ |      0       | 

Define the following events:
- $X=0$
- $X=1$
- $X=2$

$P(X=x)=P(X=0)=\frac{4}{9}$
$P(X=x)=P(X=1)=\frac{2}{9}+\frac{2}{9}=\frac{4}{9}$
$P(X=x)=P(X=2)=\frac{1}{9}$

Possible values of X with their probability 👆
The function $f(x)=P(X=x)$ called the *Probability Distribution Function* or *Probability Mass Function*

*Probability Mass Function* must satisfies these conditions:
- $0 \le p(x) \le 1$
- $\sum_{all x} p(x) = 1$

<span style='color:pink'>Example</span>

A shipment of 8 similar microcomputers to a retail outlet contains 3 that are defective and 5 are non-defective. If a school makes a random purchase of 2 of these computers, find the probability distribution of the number of defectives.

**Solution**

$n(S)=$$8\choose{2}$$=28$

5 *Non-Defective*
3 *Defective*

$n(NN)={}_5C_2 \times {}_3C_0=10$ *of ways to select 2 non-defectives*
$n(ND)={}_5C_1 \times {}_3C_1=15$ *of ways to select 1 non-defectives and 1 defective*
$n(DN)={}_5C_1 \times {}_3C_1=15$ same as 👆
$n(DD)={}_5C_0 \times {}_3C_2=3$ *of ways to select 2 defectives*

$P(X=0)=\frac{10}{28}$
$P(X=1)=\frac{15}{28}$
$P(X=2)=\frac{3}{28}$

Probability Distribution:

|  $x$  |   $P(X = x)$    |
|:-----:|:---------------:|
|  $0$  | $\frac{10}{28}$ |
|  $1$  | $\frac{15}{28}$ |
|  $2$  | $\frac{3}{28}$  |
| *Total* | $1$                |

![[4- Random Variables and Probability Distributions-1673275351283.jpeg|300]]

<span style='color:red'>Definition</span>

*Cumulative Distribution Function* (CDF), $F(x)$, of a *discrete random variable* $X$ with the probability distribution function $f(x)$ is given by:
$$
F(X)=P(X\le{x})=\sum_{t\le{x}}f(t) \hspace{1cm} -\infty \lt x \lt\infty
$$

<span style='color:pink'>Example</span>

Find the CDF of the random variable $X$ of the previous example

| $x$ |     $P(X)$      |
|:----------------------:|:---------------:|
|           $0$            | $\frac{10}{28}$ |
|           $1$            | $\frac{15}{28}$ |
|           $2$            | $\frac{3}{28}$  |

For $x \lt 0$: $F(x)=0$
For $0 \le x \lt 1$: $F(x)=\frac{10}{28}$
For $1 \le x \lt 2$: $F(x)=\frac{10}{28}+\frac{15}{28}=\frac{25}{28}$
For $x \ge 2$: $F(x)= \frac{10}{28}+\frac{15}{28}+\frac{3}{28}= 1$

The CDF of the random variable $X$

![[4- Random Variables and Probability Distributions-1673275524548.jpeg|300]]

<span style='color:lightgreen'>Notes</span>

$P(a \lt X \le b)=P(X \le b)-P(X\le a)=F(b)-F(a)$
$P(a \le X \le b)=P(a \lt X \le b)+P(X=a)=F(b)-F(a)+f(a)$
$P(a \lt X \lt b)=P(a \lt X \le b)-P(X=b)=F(b)-F(a)-f(b)$

---

<span style='color:red'>Continuous Probability Distributions</span>

A continuous random variable $X$ there exists a non-negative function; called **Density Function**. through we which we can find probablities of events expressed in term of $X$.

The total area under the curve of $f(x)=1$

$area=\int_{-\infty}^{\infty}f(x)dx=1$

$P(a \lt X \lt b)=\int_{a}^{b}f(x)dx$

*Probability Density Function* must satisfies these conditions:
- $f(x) \ge 0$
- $\int_{-\infty}^{\infty}f(x)dx=1$

<span style='color:red'>Definition</span>

*Cumulative Distribution Function* (CDF), $F(x)$, of a *continuous random variable* $X$ with the probability density function $f(x)$ is given by:

$$
F(X)=P(X \le x)=\int_{-\infty}^{x}f(t)dt \hspace{1cm} -\infty \lt x \lt \infty
$$
$$
P(a \lt X \le b)=P(X \le B)-P(X \le a)=F(b)-F(a)
$$

