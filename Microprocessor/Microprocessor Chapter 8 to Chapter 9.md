## Chapter 8: 8086/8088 Hardware Specifications

8086 is a 16-bit microprocessor with a 16-bit data bus. While 8088 is a 16-bit microprocessor, it has 8-bit data bus
- 8086 has pin connections AD0 - AD15
- 8088 has pin connections AD0-AD7

**Pin connection AD0-AD7 (8088)**
8088 address/data bus lines are **multiplexed**.
When **ALE** is 1, it will contain an **address**, when 0 it will contain **data**

**Pin connections AD8-AD15 (8086)**
8086 address/data bus lines are **multiplexed**.
When **ALE** is 1, it will contain an **address**, when 0 it will contain **data**

##### BUS TIMING

Operation of the bus signals and the **basic read/write timing** of the 8086/8088.

If data are **written to memory** the processor:
- **outputs** the memory address on the address bus
- **outputs** the data to be written on the data bus
- **issues** a write (WR) to memory

![[Microprocessor Chapter 8-1669101984386.jpeg|500]]

If data are read from memory the processor:
- outputs the memory address on the address bus
- issues a read memory signal (RD)
- accepts the data via the data bus

![[Microprocessor Chapter 8-1669102099703.jpeg|500]]

---
#### INT 10H and INT 21H

**INT 10H**
- Clearing the screen
- Changing cursor location

Monitor screen in IBM PC is 80 columns and 25 rows.
Or in Hex 4F columns and 18 rows.

1: **Clearing the screen**
Function 06H
AL = 00H
BH = 07H
CX = 0000
DL = 79
DH = 24

```armasm
MOV AH 06
MOV AL, 00 # entire page
MOV BH, 07 # normal attribute
MOV CX, 00 # starting point
MOV DH, 24 # end point in row
MOV DL, 79 # end point in column
INT 10H
```

OR

```armasm
MOV AX, 0600
MOV CX, 00
MOV BH, 07
MOV DX, 184FH
INT 10H
```

2: **Setting the cursor**
Function 02H
Position is set in DX (DH: row, DL: column)

```armasm
MOV AX, 0200H
MOV BH, 0 # page 0
MOV DX, 0C27H
INT 10H
```

**INT 21H**
- String output
- Character output
- Character input
- String input

1: String output
Function 09
DX hold offset of string

```armasm
MOV AH, 09H
MOV AL, 00
MOV DX, OFFSET STR
INT 21H
```

2: Character output
Function 02H
Character is in DL

```armasm
MOV AX, 0200H
MOV DL, 'A'
INT 21H
```

3: Character input
Function 01H
Character is stored in AL,
```armasm
MOV AX, 0100H
INT 21H ; AL = inputted char
```

4: String input
Function 0AH
String will be stored in DX
```armasm
DATA1 DB 6,?,6 DUP(FF)
MOV AX, 0A00H
MOV DX, OFFSET DATA1
INT 21H
```

**Summary**

**INT 10H**
**Set cursor position**:
- Function 02H
- BH : page number
- DX : row:column

**Scroll (Clear) screen:**
- Function 06H
- BH: display attribute
- CX: Start of page (row:column)
- DX: End of page (row:column)

**INT 21H**
**String output:**
- Function 09H
- DX: Offset of string

**Character output:**
- Function 02H
- DL: character to print

**Character input:**
- Function 01H
- AL: inputted character

**String input:**
- Function 0AH
- DS:DX: hold the offset of inputted string

Example
Write a program to write a string and clear the screen again
and set cursor to center and print a character.

```armasm
.MODEL SMALL
.STACK 64
.DATA
    STR DB "Hello World$"
    IN_STR DB 6,?,6 DUP(0FFH)
.CODE
MAIN PROC FAR
    MOV AX, @DATA
    MOV DS, AX
    XOR AX, AX
    
    MOV AX, 0A00H
    MOV DX, OFFSET IN_STR
    INT 21H
    
    MOV DX, OFFSET IN_STR
    MOV AH, 09H
    INT 21H
    
    MOV AX, 0600H
    MOV BH, 07H
    MOV CX, 0000
    MOV DH, 24
    MOV DL, 79
    INT 10H
    
    MOV AX, 0200H
    MOV BH, 0
    MOV DH, 12
    MOV DL, 39
    INT 10H
    
    MOV AX, 0200H
    MOV DL, 'A'
    INT 21H
MAIN ENDP
END MAIN
```

