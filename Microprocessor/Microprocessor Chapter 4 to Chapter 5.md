### Chapter 4: Assembly Language

Program/Assembly components:
- Assembly Language Instructions
- Pseudo-Instructions (Directives)

Shell of an Assembly Language Program
```armasm
.MODE SMALL
.STACK 64
.DATA
;
; Data is here
;
.CODE
MAIN PROC FAR
	MOV AX, @DATA
	MOV DS, AX
	;
	; Code/Instruction is here
	;
	MOV AH, 4CH
	INT 21H
MAIN ENDP
END MAIN
```

**Instruction's Fields**
Four fields of an assembly instruction: `[label:] mnemonic [operands] [;comment]`

- Label name can be up to **31 characters**
- Label also refers to to line of code by name
- Directives are used by assemblers to organize the programs as well as other ouput files
- Directives do not generate any machine codes but assembly instructions do

##### Directives
- `.MODEL` selects the size of the memory model
	- options: `SMALL, MEDIUM, COMPACT, LARGE, HUGE and TINY`
- `SMALL` Maximum of 64K bytes of memory for *code* and another 64K bytes of memory for *data*
- `MEDIUM` Maximum of 64K bytes of memory for *data* and the *code* can exceed 64K bytes of memory
- `COMPACT` Maximum of 64K bytes of memory for *code* and the *data* can exceed 64K bytes of memory
- `LARGE` *data* & *code* can exceed 64K bytes of memory (but no single of data should exceed 64K bytes such as array)
- `HUGE` Everything can exceed 64K bytes of memory
- `TINY` For COM files. Data & code must fit into 64K bytes

##### Segment Definition

- CS, SS, DS and ES

##### Data Types and Data Definition

- DB (Define Byte) directive
	- Allocates memory in a byte-sized chunks
- DW (Define Word) directive
	- Allocates memory in a word-sized chunks
- DD (Define Double word) directive
	- Allocates memory in two words in size
- DQ (Define Quad word) directive
	- Allocates memory in four words in size (8 bytes)
- DT (Define Ten byte) directive
	- Allocates memory of packed BCD numbers (maximum 18 digit can be entered)

**ORG Directive**
Indicates the beginning of the offset address of the below line.
Offset address may used in data or code segments.

**DUP Directive**
Allocate an array or string

**EQU Directive**
Define a constant without occupying a memory location.

```armasm
COUNT EQU 5 ; not occupied memory locations
COUNT DB 5  ; occupied memory location
```

**BX** register is used to point and access data elements

---

### Chapter 5: Program Control Instructions

The jump group allows programmer to skip program sections and branch to any part of memory for the next instruction.

Types of jump
- Conditional jump
- Unconditional jump


**Conditional jump** instruction allows decisions based upon numerical tests.
Results are held in the flag bits, then tested by conditional jump instructions.
**LOOP** and conditional LOOP are also forms of the jump instruction.

**Unconditional Jump (JMP)**

Three types:
- Short jump
- Near jump
- Far jump

**Short jump**
- 2-byte instruction that allows jumps or branches to memory locations with +127 and -128 bytes from the addresss following the jump
- Called relative jump
- A displacement follows the opcode of short jump
- The displacement is represented by 1 byte sign number

**Near jump**
- 3-byte instruction, allows a branch or jump within ±32K bytes from the instruction in the current code segment.
- 2-byte signed displacement 

**Far jump**
- 5-byte instruction, allows a jump to any memory location within the real memory system.
- Obtain a new segment and offset address to accomplish the jump
- The bytes 2 and 3 of this 5-byte instruction contains the new offset address
- The bytes 4 and 5 of this 5-byte instruction contains the new segment address

If the control instruction pointer transferred to a memory location within the current code segment, it is called **NEAR** and also called **Intrasegment**. Only **IP** is updated

If the control instruction pointer transferred outside the current code segment, it is called **FAR** and also called **Intersegment**. So the **CS** and **IP** are updated

Indirect jump is done with register or with index
Conditional jumps is limited with **short jump** in 8086

Conditional jump test flag buts:
- Sign (S)
- Zero (Z)
- Carry (C)
- Parity (P)
- Overflow (O)

