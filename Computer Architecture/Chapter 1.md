### Register Transfer & Microoperation

Chapter outlines:
+ Register Transfer Language
+ Register Transfer
+ Bus and Memory Transfers
+ Arithmetic Microoperations
+ Logic Microoperations
+ Shift Microoperations
+ Arithmetic Logic Shift Unit


	Simple digital system is created by using a combinational and sequential circuits, and often characterized by their register and operation that they can perform.

Microoperation are the operations that affect the data in register.

Definition of internal organization of a computer:
- Set of registers and their functions
- Microoperation set
- Control signals

*Register Transfer Level* is a view perspective on how a digital system works based on how system's registers and functions interoperate.

```
R3 <-- R5
Implies that a digital system has a
data lines from the source register
(R5) to the destination register(R3)
Parallel load in the destination
register (R3) Control lines to
perform the action
```

Control signal is a predicate to do an action on register based on the result, called control function.

```
P: R2 <-- R1
means if (P = 1), then load the
the content of R1 to R2
```

![[Chapter 1-1680394208508.jpeg|500]]

Simulataneous operation can be described in register transfer language seperated with commas:

```
P: R3 <-- R5, MAR <-- IR
```

| Symbol                     | Description                     | Example     |
| -------------------------- | ------------------------------- | ----------- |
| Capital letters & Numerals | Register                        | MAR, R5, IR |
| Parentheses ()             | Part of register                | R2(0-7)     |
| Arrow                      | Transfer of information         | R2 <- R5    |
| Colon                      | Termination of control function | PQ'         |
| Comma                      | Seperate two microoperations    | ...         | 

**Connecting Registers**
Loading each register with the contents of every possible other registers are impractical which costs `n(n-1) = O(n^2)`

The bus is a centralized component that consist of a group of wires over which information is transfered (control circuit used to select source and destination registers).

So the number of multiplexer needed to construct a common bus line for *k* register of n-bit width is *n*, so each multiplexer is constructer for each common bit of the registers.

Transfering the data that set in the bus line to a destination register can be constructed by placing a decoder with enable and connect the output of it to all register.

Three-State Bus Buffers
Another way to construct a bus system without a multiplexer, three states signals 1, 0 and *high-impedance*.

![[Chapter 1-1680405993059.jpeg|400]]

Bus Transfer In RTL - Whether or not to explicitly mention that the data transfered to the but or not

```
BUS <-- R2, R1 <-- BUS
```

Memory (RAM) - Thought as a *sequential circuits* containing some number of registers.

At the *register level*, it is viewed as a device, M. And accessing specific location, usually address is indexed and transfered to special memory registers (MAR, or AR).

Memory Read

```
MAR <-- R2, R1 <-- M[MAR]
```

Memory Write

```
MAR <-- R2, M[MAR] <-- R1
```

---

##### Microoperations

Computer system microoperations are of four type:
- Register transfer microop
- Arithmetic microop
- Logic microp
- Shift microop

Arithmetic microoperation:
- Addition
- Subtraction
- Decrement
- Increment

Binary Adder can extended to more multi-purpose circuit called *Binary Adder-Subtractor*.
Binary Incrementer is a half-adder with the input carry set.

Arithmetic Circuit from Truth Table:

| $S_1$ | $S_0$ | $C_{in}$ | $X$ | $Y$  |   out    |   microop    |
|:-----:|:-----:|:--------:|:---:|:----:|:--------:|:------------:|
|   0   |   0   |    0     |  A  |  B   |   A+B    |     ADD      |
|   0   |   0   |    1     |  A  |  B   |  A+B+1   | ADD W/CARRY  |
|   0   |   1   |    0     |  A  | B$'$ |  A+B$'$  | SUB W/BORROW |
|   0   |   1   |    1     |  A  | B$'$ | A+B$'$+1 |     SUB      |
|   1   |   0   |    0     |  A  |  0   |    A     |  TRANSFER A  |
|   1   |   0   |    1     |  A  |  0   |   A+1    |    INC A     |
|   1   |   1   |    0     |  A  |  1   |   A-1    |    DEC A     |
|   1   |   1   |    1     |  A  |  1   |    A     |  TRANSFER A  |

**TODO: Study this..**

![[Chapter 1-1680407438308.jpeg|400]]

Logic microoperations

16 different logic operations with 2 binary variables.
*n* binary variables means you need $2^{2^n}$ functions

![[Chapter 1-1680407831800.jpeg|400]]

Applications of Logic microoperations:
- Selective-set
- Selective-complement
- Selective-clear
- Mask (Delete)
- Clear
- Insert
- Compare

Shift Microoperation
- Logical shift
- Circular shift
- Arithmetic shift

Logical shift
- The serial input is 0
- `shl` and `shr` in RTL

Circular shift
- The serial input is the bit that is shifted out of the other end
- `cil` and `cir` in RTL

Arithemetic shift
- Mean for signed binary numbers
- Left shift **multiplies** a signed number by two
- Right shift **divides** a signed number by two
- The distinction is it keeps the MSB which is the sign bit as it is.
- Left shift must check for potential overflows
- `ashl` and `ashr` in RTL

