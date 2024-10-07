# Microprocessor and Assembly Language

2022-11-01

# Overview of Chapters

- Chapter 1: Introductory
	- Numbering and Coding Systems
	- Inside the Computer
	- History of the CPU
- Chapter 2: Architecture
	- Inside 8088/8086
	- Assembly Language
	- Program Segments
	- Deeper About Segments in 80x86
- Chapter 3: Addressing Modes
	- Register
	- Immediate
	- Direct
	- Register Indirect
	- Based Relative
	- Indexed Relative
	- Based Indexed Relative

---

# Chapter 1: Introductory

## Objectives of Chaper 1:

- Number system conversion
- Some microprocessor jargons like bit, byte, real memory system, protected mode memory system
- History of the computer
- Overview of 80x86 family
- Drawing block diagram of a computer system and explain the purpose of each block
- Describe the function of the microprocessor and detail its basic operation

Terminology:
- bit: a binary digit
- nibble: half a byte 4 bits
- byte: 8 bits
- word: 2 bytes
- kilobyte: 1028 bytes
- megabyte: 1024 kilobytes

Two types of memory used in microcomputers are RAM and ROM

RAM:
- Random Access Memory (read/write memory)
- A temporary storage of programs that is is running
- Called volatile memory

ROM:
- Read-only memory
- Contains programs and essential information to the operation of a computer
- Called Nonvolatile memory

CPU (Central Processing Unit): Its function is to execute information stored in memory.

I/O Devices: Provide a means of communicating with the CPU

**Bus**
A common group of wires that interconnect components in a computer system. It interconnect the sections of a computer system transfer address, data and control information between the microprocessor and its memory and I/O system

Three types of bus:
- Address Bus
- Data Bus
- Control Bus

**Address Bus**
Requests a memeory location from memory or an I/O location from the CPU.
If I/O is addressed, the address bus contains a 16-bit I/O address from `0000H` to `FFFFH`

**Data Bus**
Transfers information between microprocessor and its memory and I/O address space

**Control Bus**
Contains lines that select the memory or I/O and cause them to perform a read or write operation

Microprocessor (CPU) controls memory and I/O through a series of connections called *buses*

Three main tasks that a microprocessor performs:
1. Data transfer between itself and the memery or I/O systems
2. Simple arithmetic and logic operations (ALU)
3. Program flow via simple decisions

The 4004 Microprocessor
- World's first microprocessor the *Intel 4004*
- a 4-bit microprocessor-programmable controller on a chip
- Addressed 4096, 4-bit wide memory locations
- Contains 45 instructions

The 8008 Microprocessor
- Released in 1971
- Extended 8-bit version
- Addressed expanded memory of 16K bytes

The 8080 Microprocessor
- Released in 1973
- First 8-bit general purpose microprocessor
- 8080 addressed four times more memory
- 64K bytes

The 8085 Microprocessor
- Released in 1977
- Last 8-bit general-purpose microprocessor
- Main advanteages were its internal clock generator, system controller and higher clock frequency

The 8086 and 8088 Microprocessor
- Released in 1978 (8086), a year after 8088 released
- 16-bit microprocessor
- 8086 & 8088 addressed 1M byte of memory
- 4-byte or 6-byte instruction cache or queue that prefetched instructions before they were executed

The 80286 Microprocessor
- Released in 1983
- Updated version of 8086/8088
- Addressed 16M-byte of memory

The 80386 Microprocessor
- Released in 1986
- 32-bit data bus and 32-bit memory address

The 80486 Microprocessor
- Released in 1989
- 8K-byte cache memory

The Pentium Microprocessor
- Labled the P5 or 80586
- Cache size 16K-byte
- 8K-byte instruction cache and data cache
- Memory up to 4G bytes
- Data bus width increased to a full 64 bits


The Pentium Pro Microprocessor
- Labled the P6
- Internal 16K level-one (L1) cache
- 8K data, 8K for instruction
- P6 contains 256K level-two (L2) cache
- P6 uses three **execution engines**, to execute up to three instruction at a time
- Can address 4G-byte or a 64G-byte memory

The Pentium II Microprocessor
- Released in 1997, new direction for Intel

The Pentium III Microprocessor
- Faster core than Pentium II
- Pentium III with clock freq. up to 1GHz
- Additional FP instructions to support 3D graphics

The Pentium 4 Microprocessor
- Released in late 2000
- Called Core2
- 3.2 GHz fast

The Future Microprocessor (Itanium)
- 64-bit organization with the IA-64 architecture
- 128 general-purpose integer and 128 floating-point registers; 64 predicate registers

Summary
- 8080: first 8-bit general purpose
- 8086: 16-bit
- 80286: extension of the 8086 with memory 16M-byte
- 80386: first 32-bit
- 80486: full cache technology and instruction pipelining
- Pentium: superscalar technique
- Pentium Pro: move into superscalar organization
- Pentium II: MMX technology
- Pentium III: FP instructions to support 3D graphics
- Pentium 4: FP and enhancement for multimedia
- Itanium: new generation that make use of 64-bit organization with IA-64

---

# Chapter 2: Architecture

## Objectives of Chaper 1:

- Function and purpose of each program-visible register in the 8086
- Flag registers and its purpose
- Different segments of the memory

## BIU and EU

The 8086 CPU logic partitioned into two functional units namely **Bus Interface Unit** (BIU) and **Execution Unit** (EU)
The reason of seperation is increasing the processing speed

**BIU**
Interacts with memory and I/O devices in fetching the instructions and data required by the EU

**EU**
Responsible for executing the instructions of the programs and to carry out the required processing

## Pipelining

Two ways to make the CPU process information faster:
- Increase the working frequancy
- Change the internal architecture of the CPU (pipelining)

Pipelining allows CPU to fetch and execute at the same time

In 8088/8086, it is done by splitting the internal structure of the microprocessor into two sections: BIU and EU

This works only if the BIU keeps ahead of the EU; thus the BIU of 8088/8086 has a buffer or a queue
Buffer is 4 bytes in 8088 and 6 bytes in 8086

If any instruction takes to long to execute, the queue is filled to its maximum capacity and the buses will sit idle

The BIU fetches a new instruction whenever the queue has room for 2 bytes in the 6 bytes 8086 or 1 byte in the 4 bytes 8088 queue

Machine instruction is executed in the following cycles:
1. Fetch an instruction from memory (Fetch)
2. Decode the instruction (Decode)
3. Execute the instruction (Execute)

## The 8086 Programming Model

BIU registers (20-bit adder):
- `ES`
- `CS`
- `SS`
- `DS`
- `IP`

EU registers (16-bit arithmetic):
- `AX`
- `BX`
- `CX`
- `DX`
- `SP`
- `BP`
- `SI`
- `DI`
- `FLAGS`

## Multipurpose Registers

AX: 16-bit accumulator register or two 8-bit registers (AH and AL)
Used in multiplication, division and some of the adjustment instructions.

BX: a base index register sometimes holds offset address of a location in the memory.

CX: counter (general-purpose) register that holds the count for various instructions.

DX: data (general-purpose) register holds a part of the result from a multiplication or part of dividend before a division.

BP: base pointer that points to a memory location for memory data transfer

DI: destiniation index that often used to addresses string destination data for the string instruction

SI: source index that addresses source string data for the string instruction.

## Special-Purpose Registers

IP: instruction pointer the addresses the next instruction in a section of memory

SP: stack pointer that addresses an area of memory called the stack, it stores data through this pointer

## Segment Registers

Generate memory addresses when combined with other registers in the microprocessor

CS (Code Segment): holds code (programs and procedures) used by the microprocessor

DS (Data Segment): contains most data used by a program
Data are accessed by contents of other registers that holds the offset address

SS (Stack Segment): defines the area of memory used for the stack
- Stack entry point is determined by the stack segment and stack pointer registers
- The BP register also addresses data within the stack segment

ES (Extra Segment): an additional data segment used by some instructions to holds destination data

## Registers

Registers are used to store information **temporarily** and could be 2 bytes or 1 byte

The general-purpose registers in 8088/86 microprocessors can be accessed as either 16-bit or 8-bit registers while other registers can only be accessed as the full 16-bit

```js
#----------------#
|       AX       |
|----------------|
|   AH   |   AL  |
#----------------#
```

AX: 16-bit
AH and AL: 8-bit

**Summary of Registers:**
```txt
- General-Purpose (Data)
	- AX
	- BX
	- CX
	- DX
- Pointer
	- SP
	- BP
- Index
	- SI
	- DI
- Segment
	- ES
	- CS
	- DS
	- SS
- Instruction
	- IP
- Flag
	- FLAGS (ZF,SF,OF,...)
```

---

# Continuation of Chapter 2: Assembly Language and Segments

## MOV instruction

Copies data from one location to another

```txt
MOV destination, source
```

Notes:
- Source and destination registers must be equal in size.
- Data can not be moved directly into segment register
- Values can not be loaded directly into any segment register
- Moving a value that is too large causes error

To load a value into a segment, load it first to nonsegment register then to a segment

```armasm
MOV AX, 552FH
MOV DS, AX
```

## ADD instruction

Adds the source to the destination

```txt
ADD destination, source
```

```armasm
MOV AL, 50H
MOV BL, 20H
ADD AL, BL ; AL=AL+BL
```

## Program Segments

**Code Segment**: Assembly langauge instruction

**Data Segment**: Stored information that need to be processed by the instruction in the code segment

**Stack Segment**: Used to store **temporary** information

**Extra Segment**: Used to store **temporary** segment

![[Pasted image 20221012011405.png]]

## Logical Address and Physical Address

Three types of addresses:
- Physical address
- Offset address
- Logical address

**Physical address**
20-bit address that actually put on the address pins of the 8086 microprocessor
It ranges from 00000H to FFFFFH for 8086 and real-mode 286, 386 and 486 CPUs

This is actual physical location in RAM or ROM within the 1MB memory range

**Offset address**
A location within a 64K-byte segment range. Therefore, an offset address can range from 0000H to FFFFH

**Logical address**
Consist of a segment value and an offset address

## Code Segment

To execute a program, the 8086 fetches the instructions from the code segment

**Logical address** of an instruction always consists of a *CS* and an *IP* `CS:IP` format

**Physical address** for the location of the instruction is generated by shifting the *CS* left one hex digit and then adding it to the *IP* which contains the offset address

The result is 20-bit address which is called the physical address

```txt
CS: 2500
IP: 95F3

Logical address: CS:IP = 2500:95F3
Physical address: 25000+95F3 = 2E5F3
```

Example

```txt
If CS = 24F6H and IP = 634AH

Logical address: CS:IP = 24F6:634A
Offset address: 634A
Physical address: 24F60+634A = 2B2AA
Lower range: 24F60+0000 = 24F60
Upper range of CS: 24F60+FFFF = 34F5F
```

## Data Segment

In 8086, the area of memory set aside for data is called the data segment

Code segment is associated with IP while data segment uses register DS and an offset value

Assume that the offset for the data segment begins at 200H. The data is placed in memory location
```txt
DS:0200 = 25
DS:0201 = 12
DS:0202 = 15
DS:0203 = 1F
DS:0204 = 2B
```

Then program can be rewritten as

```armasm
ADD AL, [0200] ; DS:200
ADD AL, [0201] ; DS:201
ADD AL, [0202] ; DS:202
ADD AL, [0203] ; DS:203
ADD AL, [0204] ; DS:204
```

In 8086, allowed register to be as offset register for data segment:
- `BX`
- `SI`
- `DI`

```txt
DS: 7FA2H
Offset: 438EH

Physical address: 7FA20+438E = 83DAE
Lower range: 7FA20+0000 = 7FA20
Upper range for DS: 7FA20+FFFF = 8FA1F
Logical address: 74A2:438E
```

```txt
Assume that a DS register is 578C. To access a given byte of data at physical memory location 67F66. Does the data segment cover the range where the data is located? if not what changes need to be made?

Upper range of DS: 678BF
To access the location, DS must be changed
```

## Little Endian Convention

When using 16-bit data, the lower byte goes to the lower memory address and higher byte goes to the higher memory address

```armasm
MOV AX, 35F3H
MOV [1500], AX
; DS:1500 contains F3H
; DS:1501 contains 35H
```

This is called **little endian**

In big endian, higher byte goes to lower memory address and lower byte goes to higher memory address

```txt
DS:6826 = 48
DS:6827 = 22

Show the contents of register BX in the instruction
MOV BX, [6826]

According to little endian convention, register BL contains the low offset address 6826 and BH contains the high offset address 6827

BX: 2248H
```

## Stack Segment

Two main registers used to access the stack are the SS register and the SP

Pushing onto the stack
- Each push instruction executed, the contents of the register is saved at the top on the stack and stack pointer (SP) is decremented by 2 `SUB SP, 2` 
- Content must be 16-bit wide, so the SP is decremented twice

Popping from the stack
- Every pop instruction, the first 2 bytes on the top are copied to the register specified and stack pointer (SP) is incremented twice `ADD SP, 2`

## Flag Register

A 16-bit register, sometime referred to as the status register

16-bit wide, and each bit is different flag/indicator of some status of an operation

6 flags are called **conditional flags**, indicating some condition that resulted after an instruction was executed
- `CF` (Carry)
- `PF` (Parity)
- `AF` (Auxiliary carry)
- `ZF` (Zero)
- `SF` (Sign)
- `OF` (Overflow)

**Control flag** are the remaining flag and used to control the operation of instruction before they executed
- `DF` (Direction)
- `IF` (Interrupt)
- `TF` (Trap)

---

# Chapter 3: Addressing Modes

There are 7 types of addressing mode
- Register addressing mode
- Immediate addressing mode
- Direct addressing mode
- Register Indirect addressing mode
- Based relative addressing mode
- Indexed relative addressing mode
- Based indexed relative addressing mode

## Register Addressing Mode

Most common form of data addressing and it is relatively fast because memory is not accessed when this mode is executed

```armasm
MOV BX, DX
MOV ES, AX
MOV AL, BH
```

Exceptions:
- Source and destination registers must match in size
- segement-to-segment is not allowed `MOV ES,CS`
- register-to-segment is not allowed `MOV CS,AX`

## Immediate Addressing Mode

This term "immediate" implies that data immediately follow the hexadecimal opcode in the memory

```armasm
MOV AX, 1000H
MOV CX, 625 ; decimal
MOV BL, 50H ; hexadecimal
```

## Direct Addressing Mode

Moves a byte/word between a memory location and a register.

The address is the offset address and one can calculate physical address by shifting left the DS register and add the offset:

```armasm
MOV DL, [2400] ; DS:2400H into DL
```

**Address Generation** is the one which resposible for calculating the physical address

```txt
Address Generator fetchs the DS register and shift it to left and add the displacement value to it to to calculate the physical/effective address
```


![[Pasted image 20221012032244.png]]

## Register Indirect Addressing Mode

Same as *Direct Addressing Mode* but the offset is held in the following registers: *BP, BX, DI, SI*

```armasm
MOV [BX], CL ; Effective address: DS:BX = DS*10+BX
```

![[Pasted image 20221012034010.png]]

![[Pasted image 20221012035626.png]]

*BP offset register is used to access stack segment memory location*

## Based Relative Addressing Mode

In this addressing mode, base registers `BX` and `BP` as well as a displacement value are used to calculate the *effective address*

`BX` register is used to physical address (PA) are `DS` for `BX` and `SS` for `BP`

```armasm
MOV CX, [BX] + 10
; OR
MOV CX, [BX+10]
; OR
MOV CX, 10 [BX]
```

```armasm
MOV AL, [BP] + 5
```

## Index Relative Addressing Mode

Same as *Based Relative Addressing Mode* with exeception of that registers `DI` and `SI` hold the offset address

```armasm
MOV DX, [SI] + 5  ; PA = DS*10 + SI + 5
MOV CL, [DI] + 20 ; PA = DS*10 + DI + 20
```

## Based Index Addressing Mode

Combination of based and indexed addressing modes derives a new addressing mode *Based Index Addressing Mode*

In this mode, only one index register and one base register are used

```armasm
MOV CL, [BX][DI]+8
MOV CH, [BX][SI]+20
MOV AH, [BP][DI]+12
MOV AH, [BP][SI]+29
; OR
MOV AH, [BP+SI+29]
```

```armasm
MOV CL, [SI][DI] ; illegal
```


## Default Segment and Overrides

| Segment Register | CS  |    DS    |    ES    |  SS   |
|:----------------:|:---:|:--------:|:--------:|:-----:|
| Offset register  | IP  | BX SI DI | BX SI DI | BP SP |


In 8088/8086 CPU, it allows the program to override the default segment and use any segment register.

It is done like the following

```armasm
MOV AL, [BX] ; PA = DS*10+BX
```

To override DS register:

```armasm
MOV AL, ES:[BX] ; PA = ES*10+BX
```

```armasm
MOV AX, CS:[BP] ; SS is overridden
MOV AX, CS:[SI] ; DS is overridden
MOV AX, ES:[DI] ; DS is overridden
MOV AX, DS:[SP] ; SS is overridden
```

## Note

Difference between Physical Address and Effective Address

Physical Address:
- Actual address
- Concern of the operating system
- Generated by the hardware

Effective Address:
- Offset address
- Concern of the program
- It is virtual address that is generated the program

