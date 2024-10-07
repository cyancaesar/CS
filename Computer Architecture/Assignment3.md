### Assignment 3 solutions

**Computer Architecture**

Solutions for **Q1**

a) $256 \times 2^{10}$ word = $2^8 \times 2^{10}$ = $2^{18}$
- Address part has 18 bits
- Opcode part: $32-(18+6+1)=32-25=7$ bits
- Register code part: $2^6$ = 6 bits

b)

![[Homework3-1683570908202.jpeg|375]]

c)
- Data = 32 bits
- Address: 18 bits

Solutions for **Q2**

- Direct address needs 1 reference which is an *operand*
- Indirect address needs 2 references which are *EA* and an *operand*

Solutions for **Q3**

a) Load operation (Read from memory)
$$
IR \longleftarrow M[AR]
$$
b) Transfer temporary register to program counter
$$
PC \longleftarrow TR
$$
c) Store operation (Write to memory)
$$
IR \longleftarrow M[AR]
$$
d) ALU activated
$$
AC \longleftarrow AC+DR
$$
Solutions for **Q4**

a)

$$
AC \longleftarrow PC
$$
- Selection: $010$
- LD: $AR$
- Mem. operation: Idle
- Adder: Idle

b)

$$
IR \longleftarrow M[AR]
$$
- Selection: $111$
- LD: $IR$
- Mem. operation: Read
- Adder: Idle

c)

$$
M[AR] \longleftarrow IR
$$
- Selection: $110$
- LD: Idle
- Mem. operation: Write
- Adder: Idle

d)

$$
AC \longleftarrow DR,DR \longleftarrow AC
$$
- Selection: $100$
- LD: $AC,DR$
- Mem. operation: Idle
- Adder: Idle

Solutions for **Q5**

a) PC cannot be used as an address to memory, AR is used for that
$$
T_0:AR \longleftarrow PC
$$
$$
T_1:IR \longleftarrow M[AR]
$$

b) TR is not connect with the ALU, DR is the only register connect to the ALU and AC.

$$
T_0:DR \longleftarrow TR
$$
$$
T_1:AC \longleftarrow AC+DR
$$

c) The ALU result is stored to AC not on DR
$$
T_0:AC \longleftarrow DR, DR \longleftarrow AC
$$
$$
T_1:AC \longleftarrow AC+DR
$$
$$
T_2:AC \longleftarrow DR, DR \longleftarrow AC
$$

---

Solutions for **Q6**

a) $0001$ $0000$ $0010$ $0100$ $\longrightarrow$ MRI
b) $1011$ $0001$ $0010$ $0100$ $\longrightarrow$ MRI
c) $1111$ $0000$ $0100$ $0000$ $\longrightarrow$ I/O Instruction
d) $0111$ $0000$ $0010$ $0000$ $\longrightarrow$ RRI

Solutions for **Q7**

The content of AC in the basic computer is hexadecimal **A937** and the initial value of
E is **1**. Determine the contents of AC, E, PC, AR, and IR in hexadecimal after the
execution of the CLA instruction. Repeat **11** more times, **starting from each one** of the
**register-reference instructions**. The initial value of PC is hexadecimal **021**

|    Instr.     |  E  |  AC  | PC  | AR  |  IR  |
|:-------------:|:---:|:----:|:---:|:---:|:----:|
| initial state |  1  | A937 | 021 |  -  |  -   |
|      CLA      |  1  | 0000 | 022 | 800 | 7800 |
|      CLE      |  0  | A937 | 022 | 400 | 7400 |
|      CMA      |  1  | 56C8 | 022 | 200 | 7200 |
|      CME      |  0  | A937 | 022 | 100 | 7100 |
|      CIR      |  1  | D49B | 022 | 080 | 7080 |
|      CIL      |  1  | 526F | 022 | 240 | 7040 |
|      INC      |  1  | A938 | 022 | 020 | 7020 |
|      SPA      |  1  | A937 | 022 | 010 | 7010 |
|      SNA      |  1  | A937 | 022 | 008 | 7008 |
|      SZA      |  1  | A937 | 022 | 004 | 7004 |
|      SZE      |  1  | A937 | 022 | 002 | 7002 |
|      HLT      |  1  | A937 | 022 | 001 | 7001 |


Solutions for **Q8**

|         | PC  | AR  |  DR  |  AC  |  IR  |
|:-------:|:---:|:---:|:----:|:----:|:----:|
| Initial | 021 |  -  |  -   | A937 |  -   |
|   T0    | 021 | 021 |  -   | A937 |  -   |
|   T1    | 022 | 021 |  -   | A937 | 0083 |
|   T2    | 022 | 083 |  -   | A937 | 0083 |
|   T3    |  -  |  -  |  -   |  -   |  -   |
|   T4    | 022 | 083 | B8F2 | A937 | 0083 |
|   T5    | 022 | 083 | B8F2 | A832 | 0083 |

- $PC=022$
- $AR=083$
- $DR=B8F3$
- $AC=A832$
- $IR=0083$

Solutions for **Q9**

|         | PC  | AR  |  DR  |  AC  |  IR  |
|:-------:|:---:|:---:|:----:|:----:|:----:|
| Initial | 10A |  -  |  -   | 1A42 |  -   |
|   T0    | 10A | 10A |  -   | 1A42 |  -   |
|   T1    | 10B | 10A |  -   | 1A42 | 920F |
|   T2    | 10B | 10A |  -   | 1A42 | 920F |
|   T3    | 10B | AFF |  -   | 1A42 | 920F |
|   T4    | 10B | AFF | 24A1 | 1A42 | 920F |
|   T5    | 10B | AFF | 24A1 | 3EE3 | 920F |


Solutions for **Q10**

a)
- $IR=932E$
- $AC \leftarrow AC \hspace{0.2cm} ADD \hspace{0.2cm} DR$

b)
- $AC \leftarrow AC + DR$

c)
- $PC=3B0$
- $AR=9AC$
- $DR=8B9F$
- $AC=0A62$
- $IR=932E$
- $E=1$
- $I=1$
- $SC=0$

Solutions for **Q11**

![[Homework3-1683577859570.jpeg|350]]

Solutions for **Q12**

a) $AND$

![[Homework3-1683578928722.jpeg|350]]

b) $LDA$

The process is the same as above, we just start changing
instructions from T4.

![[Homework3-1683578954620.jpeg|350]]

c,d) $CLA$ and $CMA$

![[Homework3-1683579031724.jpeg|350]]

---

Solutions for **Q14**

Boolean expression for PC register
![[Homework3-1683579842050.jpeg|350]]

The control gates
![[Homework3-1683579871120.jpeg|350]]

Solution for **Q15**

![[Homework3-1683580278193.jpeg|350]]

