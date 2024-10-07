### Assembly Language

Each line consists of three columns
- Label field
	- address consists of up to 3 characters
	- used for jumping
- Instruction field
	- MRI
	- MRI consists of two or three symbols seperated by spaces
- Comment field

**Pseudo-Instruction**
- ORG N
	- Hex N in the memory location
- END
	- End of symbolic program
- DEC N
	- Signed decimal number N to be converted to the binary
- HEX N
	- Hex number N to be converted to the binary

---

**Assembler**
- Source Program - Symbolic Assembly Language Program
- Object Program - Binary Machine Language Program
- 1st pass: generate the user-defined symbols table
- 2nd pass: binary translation

---

##### Logic operation

Program for OR operation:
With only AND, CMA and CLA

```armasm
LDA A   ; Load 1st operand
CMA     ; Complement 1st operand
STA TMP ; Store 1st operand to temp loc
LDA B   ; Load 2nd operand
CMA     ; Complement 2nd operand
AND TMP ; AND 1st operand with 2nd operand A` AND B`
CMA     ; Complement to get A or B
```

Program for shift operation

BC only has Circular Shift only *CIL* and *CIR*

Shift-right:
```armasm
CLE
CIR
```

Shift-left:
```armasm
CLE
CIL
```

Arithmetic right-shift

```armasm
CLE ; clear E
SPA ; skip if AC is positive
CME ; complement E
CIR ; circular shift E and AC
```

