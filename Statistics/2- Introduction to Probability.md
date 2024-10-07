## Probability and Statistics

26 Dec 2022

---

#### Chapter 2

(**Experiment**) Some procedure (or process) that we do and it results in an outcome.

(**Sample Space**) The set of ALL possible outcomes of a statistical experiment and denoted by *S* or *Ω*.
Each outcome of the *sample space* S is called *sample point*.

**Events**
An event *A* is a subset of the sample space *S* `A ⊆ S`.
- An event *A* occurs if the outcome of the experiment is an element of A.
- `φ ⊆ S` is an event and called the **impossible event**
- `S ⊆ S` is an event and *S* is called the **sure event**

<span style='color:pink'>Example</span>

Experiment: Selecting a ball from a box containing 6 balls numbered (1,2,3,4,5,6).

This experiment has 6 possible outcomes: `S = {1,2,3,4,5,6}`

Events:
- E1 = getting an event number = `{2,4,6} ⊆ S`
- E2 = getting an odd number = `{1,3,5} ⊆ S`
- E3 = getting 1 or 3 = `{1,3} ⊆ S`
- E4 = getting a number less than 4 = `{1,2,3} ⊆ S`
- E5 = getting a negative number = `{} = φ ⊆ S`
- E6 = getting a number less than 10 = `S ⊆ S`

<span style='color:lightgreen'>Notation</span>

```
n(Ω) = no. of outcomes in Ω
n(E) = no. of elements in the event E
```

<span style='color:pink'>Example</span>

Experiment: Selecting 3 items from manufacturing process; each item is inspected and classified as defective (D) or non-defective (N).

Number of possible outcomes from this experiment: 8

```
S = {DDD, DDN, DND, DNN, NDD, NDN, NND, NNN}
```

Events:
- E1 = at least 2 defective = `{DDD,DDN,DND,NDD} ⊆ S`
- E2 = at most one defective = `{DNN,NDN,NND,NNN} ⊆ S`
- E3 = 3 defectives = `{DDD} ⊆ S`

---

##### Some Operations on Events

Union: `A ∪ B`
Consist of all outcomes in A or in B or in both A and B
`A ∪ B = {x ∈ S: x ∈ A or x ∈ B}`
`A ∪ B` occurs if at least on of A and B occurs.

Intersection: `A ∩ B`
Consist of all outcomes in both A **and** B
`A ∩ B = {x ∈ S: x ∈ A and x ∈ B}`
`A ∩ B` occurs if both A and B occur together.

Complement: `A'`
Consist of all outcomes of S but no in A
`A' = {x ∈ S: x !∈ A}`

Mutually Exclusive (Disjoint)
Two events A and B are mutually exclusive (or disjoint) if and only if `A ∩ B = φ`; meaning they are no intersection between them.

---

##### Counting Sample Points

**Combinations**
Used to get the all possible number of ways of selecting *r* objects from *n* objects without regard to order.

![[2- Introduction to Probability-1672044193722.jpeg|250]]
![[2- Introduction to Probability-1672044217961.jpeg|250]]

<span style='color:lightgreen'>Notes</span>

![[2- Introduction to Probability-1672044541996.jpeg|125]]
![[2- Introduction to Probability-1672044555070.jpeg|125]]
![[2- Introduction to Probability-1672044564655.jpeg|200]]

---

##### Probability of an Event

- To every point (outcome) in the sample space of an experiment *S*, we assign a *weight* (or probability), ranging from 0 to 1, such that the sum of all weights (probabilities) equal 1
- The weight (or probability) of an outcome measures its likelihood (chance) of occurrence
- To find the probability of an event A, we sum all probabilities of the sample points in A. This sum is called the probability of the event A and denoted by `P(A)`

Definition:
1. `0 <= P(A) <= 1`
2. `P(S) = 1`
3. `P(φ) = 0`

<span style='color:pink'>Example</span>

A balanced coin is tossed twice. What is the probability that at least one head occurs:

```
S = {HH, HT, TH, TT}
E = {at least one head occurs} = {HH, HT, TH}

Since tha coin is balanced, all outcomes have the same weight.
```

| Outcome |  Weight   |
|:-------:|:---------:|
|   HH    | P(HH) = w |
|   HT    | P(HT) = w |
|   TH    | P(TH) = w |
|   TT    | P(TT) = w |
|   SUM   |  4w = 1   |

$$
w = \frac{1}{4}, \hspace{1em} P(E) = P(HH)+P(HT)+P(TH)
$$
$$
P(E) = 3 \times \frac{1}{4} = \frac{3}{4} = 0.75
$$
**Theorem**

If an experiment has `n(S) = N` equally likely different outcomes, then the probability of the event A is:
$$
P(A) = \frac{n(A)}{n(S)} = \frac{n(A)}{N} = \frac{\text{no. of outcomes in A}}{\text{no. of outcomes in S}}
$$
<span style='color:pink'>Example</span>

A mixture of candies consists of 6 mints, 4 toffees and 3 chocolates. If a person makes a random selection of one of these candies, find the probability of getting:
- (a) a mint
- (b) a toffee or chocolate

Solution

Define the following events:
- `M = {getting a mint}`
- `T = {getting a toffee}`
- `C = {getting a chocolate}`

Experiment

Selecting a candy at random from 13 candies
`n(S) = number of outcomes of the experiment of selecting candy = number of different ways of selecting a candy from 13 candies`.
$$
n(S)={13 \choose 1} = 13\text{ ways of selecting candy from 13 candies}
$$
$$
n(M) = {6 \choose 1} = 6 \text{ (mint)}
$$
$$
n(T) = {4 \choose 1} = 4 \text{ (toffee)}
$$
$$
n(C) = {3 \choose 1} = 3 \text{ (chocolate)}
$$
Now the probability of getting a **mint**:

$$
P(M) = \frac{n(M)}{n(S)} = \frac{6}{13}
$$

And the probability of getting a **toffee** or **chocolate**:

$$
P(T)+P(C)-P(T \cap C)=(\frac{4}{13})+(\frac{3}{13})=\frac{7}{13}
$$

---

##### Additive Rules: OR clause

**Theorem**
If *A* and *B* are any two events, then:
$$
P(A \cup B) = P(A)+P(B)-P(A \cap B)
$$
**Corollary 1**
If *A* and *B* are mutually exclusive (disjoint) events, then:
$$
P(A \cup B)=P(A)+P(B)
$$

**Corollary 2**
If a set of n of *A* are mutually exclusive events. then the probability is the sum of those probabilities individually.

<span style='color:lightgreen'>Notes</span>

![[2- Introduction to Probability-1672293630496.jpeg|400]]

<span style='color:pink'>Example</span>

The probability that a guy passes Mathematic is $\frac{2}{3}$, and the probability that he passes English is $\frac{4}{9}$. If the probability that he passes both courses is $\frac{1}{4}$, what is the probability that he will:
- (a) pass at least one course
- (b) pass Mathematics and fail English
- (c) fail both courses

Solution

Define the events:
- `M = {passes Mathematics}`
- `E = {passes English}`
- $P(M)=\frac{2}{4}$, $P(E)=\frac{4}{9}$, $P(M\cap E)=\frac{1}{4}$

(a) Pass at least one course:

$$
P(M \cup E) = P(M)+P(E)-P(M \cap E) = \frac{2}{4}+\frac{4}{9}-\frac{1}{4} = \frac{31}{36}
$$

(b) Pass Mathematics and fail English

$$
P(M \cap E^C) = P(M)-P(M \cap E) = \frac{2}{3}-\frac{1}{4}=\frac{5}{12}
$$

(c) Fail both courses

$$
P(M^c \cap E^c)=1-P(M \cup E) = 1-\frac{31}{36}=\frac{5}{35}
$$


**Theorem**
If *A* and $A^c$ are complementary events, then:

$$
P(A)+P(A^C) = 1
$$
$$
1-P(A)=P(A^C)
$$

---

### Extra Notes from Web

Types of Events in Probability:
- Impossible and Sure Events
- Simple Events
- Compound Events
- Independent and Dependent Events
- Mutually Exclusive Events
- Exhaustive Events
- Complementary Events
- Events with "OR"
- Events with "AND"
- Event $E_1$ but not $E_2$

