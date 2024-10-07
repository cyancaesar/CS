## What is a language

- In programming language, language is a set of sentences
- Sentences is a string of characters over alphabet
- Every C program, is a sentence of C language

```c
main() {
  printf("hello, world!\n");
}
```

- `a -> identifier`
- `b -> string`
- `c -> (`
- `d -> )`
- `e -> {`
- `f -> }`
- `g -> ;`

So the sentence is `acdeacbdgf`

## Definition of a Language

- The syntax of a language can be defined by a set of *syntax rule*.

*Parsing*: Try to match the input sentence with the structure of the language.

The structure of the language is called *parse tree*.

---

- **Syntax**: the form or structure of the expressions.
- **Semantics**: the meaning of the expression
	- What does it do
	- Is it valid?
- Both define language's definition

## General Problem of Describing Syntax

A *sentence* is a string of characters over some alphabet.

A *language* is a set of sentences.

A *lexeme* is the lowest level syntactic unit of a language `*, sum, begin`.

A *token* is a category of lexemes `identifier`.

## Formal Definition of Languages

- **Recognizers**
	- A device read the input strings and decide whether the input string belong to the language.
	- Syntax analyzer.
- **Generators**
	- A device that generate sentences of a language.

## Formal Methods of Describing Syntax

- **Context-Free Grammars** (CFG)
- **Backus-Naur Form** (BNF)

## BNF

The grammar consists of four parts:

- Set of tokens and lexemes (terminals)
- Set of non-terminals
- Start symbol
- Set of production rules

**BNF Fundamentals**

- Non-terminal: BNF abstractions
- Terminals: lexemes and tokens
- Grammar: a collection of rules (or called productions)

## BNF Rules

A rule has a LHS and RHS and consists of a terminal and non-terminal symbols.

A grammar is a finite nonempty set of rules.

An abstraction (or nonterminal symbols) can have more than one RHS.

A rule is *recursive* if its LHS appears in its RHS.

## Ambiguity in Grammars

Ambiguous if and only if it generates *sentential* form that has two or more distinct parse trees.

---

## Attribute Grammars

Context-free grammars (CFGs) cannot describe all of the syntax of programming languages.

The value of attribute grammars:
- Static semantics specification
- Compiler design (static semantics checking)

Types of attributes:
- Synthesized attribute
	- Pass up
- Inherited attribute
	- Pass down
- Intrinsic attribute

**Dynamic semantics**:
- Operational semantics
- Axiomatic semantics
- Denotational semantics

