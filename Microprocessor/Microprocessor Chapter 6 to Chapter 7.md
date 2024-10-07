## Chapter 6: Data Movment

Program to copy 5 bytes from DATA_IN to COPY

```armasm
.MODEL SMALL
.DATA
    DATA_IN DB 5h,6h,7h,8h,9h
    COPY DB 6 DUP(?)
    
.CODE         
MAIN PROC FAR
    MOV AX, @DATA
    MOV DS, AX 
    
    MOV SI, OFFSET DATA_IN
    MOV DI, OFFSET COPY
    MOV CX, 05H
    XOR AX, AX
    
    LOOP1:
    MOV AH, [SI]
    MOV [DI], AH
    INC SI
    INC DI
    DEC CX
    JNZ LOOP1
    
    MOV AH, 4CH
    INT 21H
MAIN ENDP
END MAIN
```

---

Six forms of the PUSH and POP:
- Register, Memory, Immediate
- Segment register, flags, all registers

PUSHA and POPA (all registers)

PUSH transfers 2 bytes (word) at a time

PUSHA in order:
- AX
- CX
- DX
- BX
- SP
- BP
- SI
- DI

PUSHF (all flags)

Stack memory is maintaned by two registers
- Stack Pointer (SP)
- Stack Segment (SS)

Pushing a word: high order (8-bit) placed at SP-1 and low order placed at SP-2

```txt
PUSH BX places the contents of BX onto the stack;
assume that SS = 0300H, SP = 0800H, and BX = 1234H

PA = 03000H + 0800H = 03800H

12 is placed at 037FFH (SP-1)
34 is placed at 037FEH (SP-2)

After the instruction, the SP is decremented by 2 (07FEH)
```

The Address Generator:

```
BX = 1234H
SP = 0800H
SS = 0300H

(SS * 10) + SP = 03000H + 0800H = 03800H #

PUSH BX
037FF: 12
037FE: 34
SP = 07FE
```

PUSHA requires 16 bytes of stack memory space to store all eight 16-bit registers. (SP is decremented by 16 bytes).

```
Example
SP = 1236
AX = 24B6
DI = 85C2
DX = 5F93
PUSH AX
PUSH DI
PUSH DX
-----
```

When POP happens:
- low-order 8 bits are removed from the location addressed by SP
- high-order 8 bits are removed from the location addressed by SP+1
- then SP register is incremented by 2

 ```txt
If SS = 3500H SP = FFFEH

PA: 35000 + FFFE = 44FFE
LR: 35000H + 0000H = 35000H
UR: 35000H + FFFFH = 44FFF
LA: 3500:FFFE
```


---

## Chapter 7: Arithmetic and Logic Instructions

Arithmetics:
- Addition
- Subtraction
- Multiplication
- Division

Logic:
- AND
- OR
- XOR
- SHIFT & Rotate
- COMPARE

### Addition

- ADD and ADC (Add with Carry)
- Memory-to-Memory and Segment register not allowed
- ADD changes (ZF, SF, AF, CF, PF, OF)

Addition Types:
- Register Addition
- Immediate Addition
- Memory-to-Register Addition
- Array Addition
- Increment Addition

Register Addition
```armasm
ADD AX, BX
```

Immediate Addition
```armasm
ADD AX, 0506H
ADD BH, 05H
```

Memory-to-Register Addition
```armasm
MOV SI, OFFSET NUM
MOV AL, 0
ADD AL, [SI]
ADD AL, [SI+1]
```

Array Addition
```armasm
MOV SI, 3
MOV AL, 0
ADD, AL, ARRAY[SI] ; element 3
ADD, AL, ARRAY[SI+2] ; element 5
ADD, AL, ARRAY[SI+4] ; element 7
```

Increment Addition

Note: size of data must be described by using the BYTE PTR, WORD PTR, DWORD PTR, or QWORD PTR directive

```
INC BL

INC BYTE PTR[SI]
INC WORD PTR[SI]
INC DWORD PTR[SI]

INC DATA1
```

### Subtraction

Subtract-with-borrow (SBB) performs subtraction on numbers wider than 16-bit

Register Subtraction

```armasm
SUB AL, BL
```

Immediate Subtraction

#### Subtract with Borrow

For multi-byte (multi-word)

If carry is 0, SBB works like SUB
If carry is 1, SBB subtracts 1 from the result

---

### Multiplication and Division

Multiplication types:
- byte times byte
- word times word
- byte time word

##### Byte times Byte

Operand1 in AL
Operand2 in Register or memory
Result in AX (WORD)

##### Word times Word

Operand1 in AX
Operand2 in Register or memory
Result in DX:AX

##### Byte times Word

Operand1 in AL (AH must = 0)
Operand2 in Register or memory
Result in DX:AX

![[Pasted image 20221101204646.png]]

---

### Division

![[Pasted image 20221101204705.png]]

---

AND

destination can be a register or in memeory
source can be a register or in memory or immediate

AND used to test zero operand


OR

destination can be a register or in memeory
source can be a register or in memory or immediate

OR used to test zero operand and check ZF flag


XOR

destination can be a register or in memeory
source can be a register or in memory or immediate

XOR used to see if two operands are equal
ZF = 1 means equal

XOR used to toggle bits of an operand

SHIFT

number of shifts in CL

SHR: right shift (0 to MSB and LSB to CF)
SHL: left shift (0 to LSB and MSB to CF)

ROTATE

ROR ROL RCR RCL
number of rotation in CL
Rotate Right ROR
LSB to MSB + LSB copied to CF
Rotate Left ROL
MSB to LSB + MSB to CF

Rotate Right Carry RCR
Rotate Left Carry RCL