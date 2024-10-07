**Keyword**: a word that is special only in certain context.
**Reserved word**: a special word that cannot be used as a user-defined name.
**Variable**: an abstraction of a memory cell.

Variable attributes:
- Name
- Address
- Value
- Type
- Lifetime
- Scope

**Binding Times**

- *Language design time* -- bind operator symbols to operation
- *Language implementation time* -- bind floating point type to a representation
- *Compile time* -- bind a variable to a type in C or Java
- *Load time* -- bind a C or C++ `static` variable to a memory cell
- *Runtime* -- bind a non-static local variable to a memory cell

**Static and Dynamic Binding**

- *Static binding*: It first occurs before run time and remains unchanged throughout program execution.
- *Dynamic binding*: It first occurs during execution or can change during execution of the program.

**Type Binding**

Two kinds of declarations:
- Explicit declarations: program statement used for declaring the types of a variables
- Implicit declarations: default mechanism for specifying types of variables through default conventions

Three kinds of type bindings:
- Static type binding
- Dynamic type binding
- Type inference

Lifetime of a variable: the time during which it is bound to a particular memory cell

- Allocation
- De-allocation

Categories of Variables by Lifetimes
- Static
- Stack-dynamic
- Explicit Heap-dynamic
- Implicit Heap-dynamic

*Static* -- bound to memory cells before execution begins and remains bound to the same memory cell throughout execution

*Stack-dynamic* -- bindings are created when declaration statements are elaborated at runtime

*Explicit Heap-dynamic*

- Heap: section of virtual address space reserved for dynamic memory allocation.
- Allocation and deallocation by explicit directives or operators.

*Implicit Heap-dynamic*

---

*Scope*: the range of statements over which it is visible
*Local variables*: of a program unit are those that are declared in that unit
*Nonlocal variables*: of a program unit are those that are visible in the unit but not declare there
*Global variables*: special category of nonlocal variables

**Scoping**

*Static scoping*: definition of a variable is resolved by searching its containing block or function, If fails, search the outer containing block and so on.
*Dynamic scoping*: definition of a variable is resolved by searching its containing block and if not found, then searching its calling function and if it still not found then the function which called that calling function will be searched and so on.

