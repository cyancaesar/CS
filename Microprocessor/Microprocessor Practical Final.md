##### Count 0's and 1's of a BYTE

```armasm
.MODEL SMALL
.DATA
.CODE
MOV AX, @DATA
MOV DS, AX
XOR AX, AX

MOV AH, 00H ; 1's
MOV BH, 08H ; 0's
MOV AL, 3DH ; 00111101
CLC
MOV CX, 09H

AGAIN:
    RCL AL, 1
    JNC LP_AGAIN
    INC AH
    DEC BH
LP_AGAIN:
    LOOP AGAIN
```

##### Convert BCD to ASCII

```armasm
; .CODE
MOV AL, 68H ; 6 (36 ASCII) 8 (38 ASCII)
MOV AH, AL

AND AX, 1111000000001111B ; F00FH
SHR AH, 4
OR AX, 3030H ; ADDING 3030 to AX
RET
```


##### Uppercase to Lowercase Conversion

```armasm
.MODEL SMALL
.STACK 64

.DATA
    PROMPT_1 DB 'Enter The Uppercase Letter: $\'
    PROMPT_2 DB 0DH, 0AH, 'Lowercase: $\'

.CODE
MAIN PROC
    MOV AX, @DATA
    MOV DS, AX
    
    LEA DX, PROMPT_1
    MOV AH, 9 ; print string
    INT 21H
    
    MOV AH, 1 ; read char (echo)
    INT 21H   
    MOV BL, AL ; store char to BL
    
    LEA DX, PROMPT_2
    MOV AH, 9 ; print string
    INT 21H
    
    ADD BL, 20H ; ADD 32 (0x20) to BL
    
    MOV DL, BL
    MOV AH, 2 ; print char
    INT 21H
    
    MOV AH, 4CH
    INT 21H    
MAIN ENDP
END MAIN
```

---

### Logical Operation

##### 32-bit Addition (WORD + WORD)

```armasm
; .CODE
MOV AX, 172 ; 1's number LSB
MOV BX, 100 ; 1's number MSB

MOV CX, 150 ; 2's number LSB
MOV DX, 150 ; 2's number MSB

ADD AX, CX ; LSB
ADD BX, DX ; MSB

HLT
RET
```

##### Reverse 8-bit number

```armasm
; .CODE
MOV AL, 15 ; 0000 1111
MOV CL, 04
ROL AL, CL

HLT
RET
```

##### Factorial

```armasm
; .CODE
MOV AL, 04 ; n
MOV CL, AL
DEC CL

LP:
	MUL CL
	DEC CL
	JNZ LP
HLT
RET
```

##### Seperate Word into Bytes

```armasm
; .CODE
MOV AX, 1D2BH
MOV BX, AX

AND AX, 255
AND BX, -256
MOV CL, 08H
ROR BX, CL

HLT
RET
```

##### Sum of N numbers

```armasm
; .CODE
MOV AX, 0000H
MOV CX, 0006H

LP1:
	ADD AX, CX
	DEC CX
	JNZ LP1

HLT
RET
```

##### Sum of square of N numbers

```armasm
MOV AX, 0000H
MOV BX, 0000H
MOV CX, 0006H

LP1:
	MOV AX, CX
	MUL CX
	ADD BX, AX
	DEC CX
	JNZ LP1

HLT
RET
```

##### Sum of cube of N numbers

```armasm
MOV AX, 0000H
MOV BX, 0000H
MOV CX, 0006H

LP1:
	MOV AX, CX
	MUL CX
	MUL CX
	ADD BX, AX
	DEC CX
	JNZ LP1

HLT
RET
```

##### Print A to Z

```armasm
.MODEL SMALL
.STACK 64
.CODE
MAIN PROC

	MOV DL, 'A'
	MOV AH, 2
	MOV CX, 26
LP1:
	INT 21H
	INC DL
	DEC CX
	CMP CX, 0
	JNZ LP1

    MOV AH, 4CH
    INT 21H 

MAIN ENDP
END MAIN
```

##### Print 0 to 9

```armasm
.MODEL SMALL
.STACK 64
.CODE
MAIN PROC

	MOV DL, '0'
	MOV AH, 2
	MOV CX, 0
LP1:
	INT 21H
	INC DL
	INC CX
	CMP CX, 10
	JNZ LP1

    MOV AH, 4CH
    INT 21H 

MAIN ENDP
END MAIN
```