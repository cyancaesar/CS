## Probability and Statistics

29 Dec 2022

---

### Conditional Probability

The probability of occurring an event *A* when it is known that some event *B* has occured is called the **conditional probability** of *A* given *B* and is denoted `P(A|B)`

<span style='color:red'>Definition</span>

The conditional probability if the event *A* given the event *B* is:
$$
P(A|B)=\frac{P(A\cap B)}{P(B)}=\frac{n(A\cap B)}{n(B)}
$$

<span style='color:lightgreen'>Notes</span>

![[3- Conditional Probability-1672310949064.jpeg|400]]

<span style='color:pink'>Example</span>

399 physicians are classified as given in the table below. A physician is to be selected at random.
- (1) Find the probability that:
	- (a) The selected physician is aged 40 - 49
	- (b) The selected physician smokes occasionally
	- (c) The selected physician is aged 40 - 49 **and** smokes occasionally
- (2) Find the probability that the selected physician is aged 40 - 49 given that the physician smokes occasionally

![[3- Conditional Probability-1672311192838.jpeg|425]]

Solution

`n(s) = 339` is equally likely outcomes.

Define the following events:
- `A3 = the selected physician is aged 40 - 49`
- `B2 = the selected physician smokes occasionally
- `A3 ∩ B2 = the selected physician is aged 40 - 49 and smokes occasionally`

1.a: the probability of the selected physician is aged 40 - 49
$$
P(A_3)=\frac{n(A_3)}{n(S)}=\frac{79}{339}=0.233
$$
1.b: the probability of the selected physician smokes occasionally
$$
P(B_2)=\frac{n(B_2)}{n(S)}=\frac{60}{339}=0.177
$$
1.c: the probability both aged 40 - 49 and smokes occasionally
$$
P(A_3\cap B_2)=\frac{n(A_3\cap B_2)}{n(S)}=\frac{21}{339}=0.0619
$$

2: `A3|B2` = the selected physician is aged 40 - 49 given that the physician smokes occasionally
$$
(i)\hspace{1em} P(A_3|B_2)=\frac{P(A_3\cap B_2)}{P(B_2)}=\frac{0.0619}{0.177}=0.35
$$
$$
(ii)\hspace{1em} P(A_3|B_2)=\frac{n(A_3\cap B_2)}{n(B_2)}=\frac{21}{60}=0.35
$$
$$
(iii)\hspace{1em} P(A_3|B_2)=\frac{21}{60}=0.35
$$

<span style='color:lightgreen'>Notes</span>

$P(A|B) = P(A)$ means that knowing *B* has **NO** effect on the probabililty of occurrence of *A*. In this case *A* is *independent* of *B*.

$P(A|B) > P(A)$ means that knowing *B* increases the probability of occurrence of *A*.

$P(A|B) < P(A)$ means that knowing *B* decreases the probability of occurrence of *B*.

---

**Independent Events**

<span style='color:red'>Definition</span>

Two events *A* and *B* are *independent* $\iff$ $P(A|B)=P(A)$ and  $P(B|A)=P(B)$.

Otherwise, *A* and *B* are *dependent*.

##### Multiplicative Rule

**Theorem**

![[3- Conditional Probability-1672312988198.jpeg|425]]

<span style='color:pink'>Example</span>

Suppose we have a fuse box containing 20 fuses of which 5 are defective (D) and 15 are non-defective (N). If 2 fuses are selected at random and removed from the box in succession without replacing the first, what is the probability that both fuses are defective.

Solution

Define the following events:
- `A = {the first fuse is defective}`
- `B = {the second is defective}`
- `A ∩ B = {the first fuse is defective and the second fuse is defective} = {both fuses are defective}`

$$
P(A)=\frac{5}{20}
$$
$$
P(B)=P(B|A)=\frac{4}{19}
$$
$$
P(A\cap B)=P(A)\times P(B|A)=\frac{5}{20}\times \frac{4}{19}=0.053
$$

![[3- Conditional Probability-1672313944065.jpeg|475]]

---

**Theorem**

Two events *A* and *B* are *independent* if and only if

```
P(A ∩ B) = P(A)P(B), if independent
```

Multiplicative rule for independent events.

<span style='color:lightgreen'>Notes</span>

Two events *A* and *B* are *independent* of one of the following conditions is satisfied:

![[3- Conditional Probability-1672314234491.jpeg|450]]

---

**Theorem (k = 3)**

![[3- Conditional Probability-1672742221645.jpeg|450]]

### Bayes' Rule Theorem

The events $A_1, A_2,...,A_n$ constitute a partition of the sample space S if:

![[3- Conditional Probability-1672742323258.jpeg|450]]

**Theorem: Total Probability**

If the events $A_1, A_2, ...,A_n$ constitute a partition of the sample space S such that $P(A_k) \ne 0 \text{ for k = 1,2,..,n}$

Then for any event B:
$$
P(B) = \sum_{i=1}^{n}P(A_i\cap{B}) = \sum_{i=1}^{n}P(A_i){\times}P(B|A_i)
$$

<span style='color:pink'>Example</span>

Three machines $A_1$, $A_2$ and $A_3$ make 20%, 30% and 50%, respectively, of the products. It is known that 1%, 4% and 7% of the products made by each machine, respectively, are *defective*.

If a finished product is randomly selected, what is the probability that it is defective?

Solution

Define the events
- `B = {product is defective}`
- `A1 = {A1 product}`
- `A2 = {A2 product}`
- `A3 = {A3 product}`

$$
P(A_1) = \frac{20}{100} = 0.2
$$
$$
P(A_2) = \frac{30}{100} = 0.3
$$
$$
P(A_3) = \frac{50}{100} = 0.5
$$
$$
P(B|A_1) = \frac{1}{100} = 0.01
$$
$$
P(B|A_2) = \frac{4}{100} = 0.04
$$
$$
P(B|A_3) = \frac{7}{100} = 0.07
$$
$$
P(B) = \sum_{k=1}^{3} P(A_k) P(B|A_k)
$$
$$
P(B) = (0.2\times0.001)+(0.3\times0.04)+(0.5\times0.07) = 0.049
$$

What is the probability that the product is defective and made by machine A1?
$$
P(A_1|B)=\frac{P(A_1\cap B)}{P(B)} = \frac{P(A_1)P(B|A_1)}{P(B)} = \frac{0.2\times0.01}{0.0049} = 0.0408
$$

👆 This rule is called Bayes' rule.

#### Theorem: Bayes' rule

![[3- Conditional Probability-1672755092595.jpeg|500]]

<span style='color:pink'>Example</span>

In the previous example, it is known that the selected product is *defective*, what is the probability that it is made by:
- (a) machine `A2`
- (b) machine `A3`

$$
(a)\hspace{2mm} P(A_2|B) = \frac{P(A_2\cap B)}{P(B)} = \frac{P(A_2)P(B|A_2)}{P(B)} = \frac{0.3\times 0.04}{0.0049} \approx 2.45
$$
$$
(b)\hspace{2mm} P(A_3|B) = \frac{P(A_3\cap B)}{P(B)} = \frac{P(A_3)P(B|A_3)}{P(B)} = \frac{0.5\times 0.07}{0.0049} \approx 7.14
$$

<span style='color:lightgreen'>Note</span>
$$
\sum_{k=1}^{n}P(A_k|B) = 1
$$
---

## Problem Sets

```gettext
At a college, 20% of the students take Finite Math, 30% take History, and 5% take both Finite Math and History. If a student is chosen at random, find the following conditional probabilities.
    1.  He is taking Finite Math given that he is taking History.
    2.  He is taking History assuming that he is taking Finite Math.
```

Define the following events:
- $A$ : $\{$ 20% students take Finite Math $\}$
- $B$ : $\{$ 30% students take History $\}$
- $A\cap B$ : $\{$ 5% students take both Finite Math and History $\}$

$P(A)=\frac{20}{100}$, $P(B)=\frac{30}{100}$ , $P(A\cap B)=\frac{5}{100}$

$$
P(A|B)=\frac{P(A\cap{B})}{P(B)}=\frac{0.05}{0.3}=\frac{1}{6}\approx 0.1667
$$
$$
P(B|A)=\frac{P(A\cap{B})}{P(A)}=\frac{0.05}{0.2}=\frac{1}{4}=0.25
$$

```gettext
A student is taking two courses, history and math.

The probability the student will pass the history course is 0.75, and the probability of passing the math course is 0.65. The probability of passing both is 0.5.

What is the probability of passing at least one?
```

$$
P(H)=0.75\hspace{2mm} P(M)=0.65\hspace{2mm} P(H\cap{M})=0.5
$$
$$
P(H\cup{M})=P(H)+P(M)-P(H\cap{M}) = 0.8
$$

```gettext
At a college, 60% of the students pass Accounting, 70% pass English, and 30% pass both of these courses. If a student is selected at random, find the following conditional probabilities.
    1.  He passes Accounting given that he passed English.
    2.  He passes English assuming that he passed Accounting.
```

```gettext
Consider a family of three children. Find the following probabilities.
```

$S=\{$ BBB, BBG, BGB, BGG, GBB, GBG, GGB, GGG $\}$

1: $P($two boys | first born is a boy$)$

Events:
- $A=$ $\{$ first born is a boy $\}$ = $\{$ BBB, BBG, BGB, BGG $\}$
- $B=$ $\{$ two boys $\}$ = $\{$ BBG, BGB, GBB $\}$
- $A\cap{B}$ = $\{$ BBG, BGB $\}$

$P(A)=\frac{n(A)}{n(S)}=\frac{4}{8}=\frac{1}{2}$
$P(B)=\frac{n(B)}{n(S)}=\frac{3}{8}$
$P(B|A)=\frac{P(A\cap{B})}{P(A)}=\frac{0.25}{0.5}=0.5$

