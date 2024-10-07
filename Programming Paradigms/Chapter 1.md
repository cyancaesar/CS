## Programming Domain

- Scientific applications
	- Large numbers of floating point computation
	- Array-based languages such as Fortran
- Business applications
	- Produce reports, use decimal numbers and characters
	- COBOL
- Artificial intelligence
	- Symbols, use of linked lists
	- LISP
- Systems programming
	- Demanding efficiency
	- C
- Web software
	- Markup, scripting, general-purpose

Language evaluation criteria is based on three factors:
- **Readability**: programs can be read and understood
- **Writability**: ease in language that can be used to create program
- **Reliability**: respecting its specifications
- **Cost**

## Readability

- Simplicity and Orthogonality
- Data types
- Syntax considerations

## Writability

- Simplicity and Orthogonality
- Abstraction
- Expressivity

## Reliability

- Type checking
- Exception handling
- Aliasing
- Readability and writability

## Influences on Language Design

Languages are developed around the prevalent **computer architecture** called *von Neumann architecture*.

**Program design methodologies** produced new programming paradigms and by extension, new programming languages such as Java.

*Imperative languages*, most dominant, because of von Neumann computer architecture.

- Data are stored in memory
- Memory is separated from CPU
- Instructions and data are piped from memory to CPU
- Basis for imperative languages
	- Variables model memory cells
	- Assignments statement model piping
	- Iteration is efficient

Programming methodologies influences:
- 1950s and early 1960s: Simple applications; worry about machine efficiency
- Late 1960s: people efficiency became important
	- Structured programming
	- top-down design and step-wise refinement
- Late 1970s: Process-oriented to data oriented
	- Data abstraction
- Middle 1980s: Object-oriented programming
	- Data abstraction + inheritance + polymorphism

## Language Categories

- Imperative
- Functional
- Logic
- Markup/programming hybrid

## Implementation Methods

- Compilation
	- Translation into machine language; includes JIT systems
	- Large commercial applications
- Pure Interpretation
	- Interpreted by another program known as *interpreter*
- Hybrid Implementation Systems
	- Compilers and interpreters

## Compilation

Compilation proceeds into phases
- Lexical analysis: converts characters in the source program into lexical units
- Syntax analysis: transforms lexical units into *parse tree*
- Semantic analysis: generate intermediate code
- Code generation: machine code is generated

## Summary

- Criteria for evaluating programming languages
	- Readability, writability, reliability and cost
- Major influence on language design have been machine architecture and software development methodologies
- Major methods for implementing programming languages are
	- Compilation
	- Pure interpretation
	- Hybrid implementation

