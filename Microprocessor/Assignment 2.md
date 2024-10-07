## Assignment 2


**Solution Q1** :
```armasm
MOV AX, 0F000H
MOV BX, 03456H
MOV DX, 0E390H

; Give the result of the register
; and the state of ZF and CF flags

; PART 1
AND DX, AX      ; ZF = 0, CF = 0 DX = E000H
XOR AL, 76H     ; ZF = 0, CF = 0 AX = F076H
XOR AX, AX      ; ZF = 1, CF = 0 AX = 0000H
AND AH, 0FFH    ; ZF = 1, CF = 0 AX = 0000H
XOR DX, 0EEEEH  ; ZF = 0, CF = 0 DX = 0EEEH
MOV CL, 04      ; CX = 0004H
SHL AL, CL      ; ZF = 1, CF = 0 AX = 0000H 

; PART 2
MOV CL, 3       ; CX = 0003H
SHL DX, CL      ; ZF = 0, CF = 1 DX = 1C80H
OR DH, BL       ; ZF = 0, CF = 0 DX = 5H80H
AND DX, DX      ; ZF = 0, CF = 0 DX = 5H80H
OR BX, DX       ; ZF = 0, CF = 0 BX = 7ED6H
OR AX, 9999H    ; ZF = 0, CF = 0 AX = F999H
XOR BX, BX      ; ZF = 1, CF = 0 BX = 0000H
SHR DX, 1       ; ZF = 0, CF = 0 DX = 2F40H
MOV CL, 5       ; CX = 0005H
SHL BX, CL      ; ZF = 1, CF = 0 BX = 0000H
```

**Solution Q2**:

```armasm

; States of ZF and CF after CMP
; (a)
MOV BX, 2500
CMP BX, 1400 ; ZF = 0, CF = 0

; (b)
MOV AL, 0FFH
CMP AL, 6FH ; ZF = 0 CF = 0

; (c)
MOV DL, 34
CMP DL, 88 ; ZF = 0 CF = 1

; (d)
SUB AX, AX
CMP AX, 0000 ; ZF = 1 CF = 0

; (e)
XOR DX, DX
CMP DX, 0FFFFH ; ZF = 0 CF = 1

; (f)
SUB CX, CX
DEC CX
CMP CX, 0FFFFH ; ZF = 1 CF = 0
```

**Solution Q3**:

```armasm
; Indicate jump occurs or not

; (a)
MOV CL, 5
SUB AL, AL
SHL AL, CL
JNC TARGET ; JUMP OCCURS CF = 0

; (b)
MOV BH, 65H
MOV AL, 48H
OR AL, BH
SHL AL, 1
JC TARGET ; JUMP DOES NOT OCCUR CF = 0

; (c)
MOV AH, 55H
SUB DL, DL
OR DL, AH
MOV CL, AH
AND CL, 0FH
SHR DL, CL
JNC TARGET ; JUMP DOES NOT OCCUR CF = 1
```

---

**Q4**:
```
Write a program that calculates the total sum paid to a salesperson for eight months. The following are the monthly paychecks for those months: $2300, $4300, $1200, $3700, $1298, $4323, $5673, $986.
[TOTAL]: 23780 (WORD)
```

**Solution Q4**:

```armasm
; Calculate the total salary and store it in TOTAL_SUM

.MODEL SMALL
.STACK 64
.DATA
	MONTH_SALARY    DW 2300, 4300, 1200, 3700, 1298, 4323, 5673, 986
	TOTAL_SUM       DW  1 DUP(?)
	
.CODE
MAIN PROC FAR
	; Prologue
	MOV AX, @DATA
	MOV DS, AX
	XOR AX, AX
	
	MOV SI, OFFSET MONTH_SALARY
	MOV DI, OFFSET TOTAL_SUM
	MOV CL, 08
	
ADD_AGAIN:
    MOV AX, [SI]
    ADD [DI], AX
    INC SI
    INC SI
    DEC CL
    JNZ ADD_AGAIN

    XOR AX, AX
    MOV AX, [DI] ; Total Sum In AX  
	; Epilogue
	MOV AH, 4CH
    INT 21H
MAIN ENDP
END MAIN
```

---

**Q5**:
```
Write, run, and analyze the result of a program that performs the following:

(1) (a) byte1 x byte2 (b) byte1 x word1 (c) word1 x word2
(2) (a) byte1 / byte2 (b) word1 / word2 (c) doubleword / byte1
```

**Solution Q5**:

```
byte1      = 230
byte2      = 100
word1      = 9998
word2      = 300
doubleword = 100000

byte1 x byte1
8-bit x 8-bit results a 16-bit
First operand must be in AL register
Second operand could be in register or in memory
Resultant will be stored in AX register
	MOV AL, byte1
	MUL byte2
Result in AX: (59D8H)

byte1 x word1
8-bit x 16-bit results a 32-bit
The byte operand must be in AL and AX must be ZERO
the word operand could be in register or in memory
Resultant will be stored in DX:AX
MSB will be in DS
LSB will be in AX
	MOV AL, byte1
	XOR AH, AH
	MUL word1
Results in DX:AX (0023H:1694H)

word1 x word2
16-bit x 16-bit results a 32-bit
First operand must be in AX (16-bit word)
Second operand could be in register or in memory
Resultant will be stored in DX:AX
    MOV AX, word1
	MUL word2
Results in DX:AX (002DH:C468H)

byte1 / byte2
Numerator must be in AL (AH must be zero)
Denominator could be in register or in memory
Quotient is stored in AL
Reminder is stored in AH
	XOR AX, AX
	MOV AL, byte1
	DIV byte2
AL = 02 quotient
AH = 1E reminder

word1 / word2
Numerator must be in AX (DX must be zero)
Denominator could be in register or in memory
Quotient is stored in AX
Reminder is stored in DX
	XOR DX, DX
	MOV AX, word1
	DIV word2
AX = 0021H
DX = 0062H

doubleword / byte1
Double Word division by Byte is not possible
You must do another method to do this calculation
```

---

**Q6**:

```
Assume that there is a class of five people with the following grades: 69, 87, 96, 45 and 75. Find the highest grade.
```

```armasm
; Assembly program to find the highest grade in array

.MODEL SMALL
.STACK 100H
.DATA
    GRADE_ARR DB 69,87,96,45,75
    GRADE_LEN EQU $- GRADE_ARR
    GRADE_HIG DB ?
    
.CODE
MAIN PROC FAR
    
    MOV AX, @DATA
    MOV DS, AX
    XOR AX, AX
    
    MOV SI, OFFSET GRADE_ARR
    MOV DI, OFFSET GRADE_HIG
    MOV CX, GRADE_LEN
    
LOOP_AGAIN:
    CMP [SI], AL
    JNS SET_HIGH
    INC SI
    DEC CX
    JNZ LOOP_AGAIN

	MOV [DI], AL ; Save Highest Grade
    JMP EXIT
    
SET_HIGH:
    MOV AL, [SI]
    INC SI
    LOOP LOOP_AGAIN

EXIT:
    MOV AH, 4CH
    INT 21H  
MAIN ENDP
END MAIN
```

**Q7**:

```armasm
; Assembly program to find the lowest grade in array

.MODEL SMALL
.STACK 100H
.DATA
    GRADE_ARR DB 44,77,88,67,12,75
    GRADE_LEN EQU $- GRADE_ARR
    GRADE_LOW DB ?
    
.CODE
MAIN PROC FAR
    
    MOV AX, @DATA
    MOV DS, AX
    XOR AX, AX
    
    MOV SI, OFFSET GRADE_ARR
    MOV DI, OFFSET GRADE_LOW
    MOV CX, GRADE_LEN
    MOV AL, 0FFH
    
LOOP_AGAIN:
    CMP AL, [SI]
    JNC SET_LOW
    INC SI
    DEC CX
    JNZ LOOP_AGAIN
    
    MOV [DI], AL ; Save Lowest Grade
    JMP EXIT
    
SET_LOW:
    MOV AL, [SI]
    INC SI
    LOOP LOOP_AGAIN

EXIT:
    MOV AH, 4CH
    INT 21H  
MAIN ENDP
END MAIN
```

**Q8**:

```
Write a program that finds the number of zeros in a 16-bit word
```

```armasm
; Assembly program to find number of zeros in a word
; total number of zeros is stored in AL

.MODEL SMALL
.STACK 100H
.DATA
    word1 DW 0DEADH ; 1101 1110 1010 1101
    
.CODE
MAIN PROC FAR
    
    MOV AX, @DATA
    MOV DS, AX
    XOR AX, AX
    
    MOV AL, 0
    MOV BX, word1
    MOV CX, 16
    
AGAIN:
    RCL BX, 1
    JNC INCREMENT
    DEC CX
    JNZ AGAIN
    JMP EXIT
    
INCREMENT:
    INC AL
    LOOP AGAIN

EXIT:
    MOV AH, 4CH
    INT 21H      
MAIN ENDP
END MAIN
```