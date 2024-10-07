- Lexical Analysis
- The Parsing Problem
- Recursive-Descent Parsing
- Bottom-Up Parsing

**Lexical Analyzer:** A pattern matcher for character strings.

- First entry in "parser"
- Identifies substrings called *lexemes* and categorize it as *token*

Three approaches to build a lexical analyzer

- Write a formal description of the tokens.
- Design a state diagram that describes the tokens and write a program that implements the state diagram.
- Design a state diagram that describes the tokens and hard-construct a table-driven.

Two types of parsers
- Top down - produce parse tree, begin at the root
- Bottom up - produce parse tree, begin at the leaves


---

## Top-down Parsers



Two common top-down parsing algorithms:

- Recursive descent - a coded implementation
- LL parsers - table driven implementation

Recursive Descent:
- Backtracking
- Non-backtracking
	- Predictive Parser
	- LL Parser

In *Predictive Parser*: If the LHS and the head of RHS are the same, then the *production* is left recursive.

A grammar is called left recursive if it possesses an immediately left recursive production.

A grammar is called indirect left recursive if it string derive to a string whose head is that symbol.

## LL Parser - First and Follow

First Set Rules
- If x is a terminal, then FIRST (x) = {'x'}
- If x -> Є, is a production rule, then add Є to FIRST (x)
- If X -> Y1 Y2 Y3...Yn is a production,
	- FIRST (X) = FIRST (Y1)
	- IF FIRST (Y1) contains Є then FIRST (X) = { FIRST (Y1) - Є } U { FIRST(Y2) }
	- If FIRST (Yi) contains Є for all i = 1 to n, then add Є to FIRST (X)

