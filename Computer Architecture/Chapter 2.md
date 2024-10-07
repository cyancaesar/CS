### Basic Computer Organization And Design

Keys:
- Instruction codes
- Computer Registers
- Computer Instructions
- Timing and Control
- Instruction cycle
- Memory Reference Instructions (MRI)
- Input-Output and Interrupt
- Complete Computer Description
- Design of Basic Computer
- Design of Accumulator Logic

---

M. Morris Mano introduced a simple processor model, called the **Basic Computer**

Two components in the basic computer:
- Processor
- Memory

Memory has 4096 words in it
- $4096 = 2^{12}$
- Each word is 16 bits long

---

**Program**: A sequence of machine instructions
**Machine Instruction**: A group of bits that tells the computer to perform a specific operation (a sequence of micro-operation)

Instructions of a program are stored in memory
The CPU reads the next instruction from memory
Instruction is placed in Instruction Register (IR).

Control circuitry in control unit then translates the instruction into the sequence of microoperations.

**Instruction Format**

Divided into two parts:
- Opcode
- Address

12 bits needed to specify which memory address the instruction will use.
At bit 15 is for addressing mode (0: direct, 1: indirect)
remaining 3 bits is for opcode

```
addrMode + opcode | memory address
|----|------------|
|0000|000000000000|
|----|------------|
```

**Addressing Modes**
- Direct address: address in memory of the data to use
- Indirect address: address in memory of the address of the data to use

Effective Address: Address directly be used without any modifications

![[Chapter 2-1683399788883.jpeg|275]]
![[Chapter 2-1683399803272.jpeg|275]]

---

**Processor Registers**

Size: 16
- DR - data register - holds memory operands
- AC - accumulator - processor register
- IR - instruction register - instruction code
- TR - temporary register - temporary data

Size: 12
- AR - address register - address for memory
- PC - program counter - address of next instruction

Size: 8
- INPR - input register - input character
- OUTR -output register - output character

		Registers in the Basic Computer are connected using a bus

**Basic Computer Instruction Format**
- Memory-Reference Instructions (OP-code = 000 ~ 110)
- Register-Reference Instructions (OP-code = 111, I = 0)
- Input-Output Instructions (OP-code = 111, I = 1)

---

**Control Unit**

Translates from machine instructions to the control signals for the microoperations that implement them.

Two implementation of the Control units:
- Hardwired Control
- Microprogrammed Control

---

#### Instruction Cycle

1. Fetch an instruction from memory
2. Decode the instruction
3. Read the effective address from memory if the instruction has an indirect address
4. Execute the instruction

![[Chapter 2-1683406745017.jpeg|500]]

![[Chapter 2-1683408874158.jpeg|475]]

Memory-Ref inst. are 7 instructions, from $D_0$ to $D_7$

---

![[Chapter 2-1683491223770.jpeg|450]]
![[Chapter 2-1683491284422.jpeg|450]]

---

## Fetch & Decode

![[Chapter 2-1683494235257.jpeg|425]]
![[Chapter 2-1683494263084.jpeg|550]]

