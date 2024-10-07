Enumeration: Aid for readability
*Array*: homogeneous aggregate of data elements.

**Subscript Binding**
*Static*: subscript ranges are statically bound and storage allocation is static
*Fixed Stack-dynamic*: subscript ranges are statically bound, but allocation is done at declaration time
*Fixed Heap-dynamic*: storage binding is dynamic but fixed after allocation
*Heap-dynamic*: binding of subscript ranges and storage allocation is dynamic and can change any number of times

*Heterogeneous array*: The elements need not to be of the same type
*Rectangular array*: Multi-dimensioned array in which the rows have the same number of elements and all columns have the same number of elements
*Jagged array*: has rows with varying number of elements
*Associative array*: unordered collection of data elements that are indexed by an equal number of values called keys
*Slice*: substructure of an array

---

*Tuple*: Like records except that the elements are not named
*'Python' Lists*: Mutable

Pointers problems:

- Dangling pointers: points to a heap-dynamic variable that has been deallocated
- Lost heap-dynamic variable: Allocated heap-dynamic variable that is no longer accessible to the user program

A program that creates garbage has a *memory leak*

**Heap management**

- Reference counters (eager approach)
- Mark-sweep (lazy approach)

Ways to make an object eligible for garbage collection
- Nullify reference variable
- Re-assigning reference variable
- Object created inside method
- Island of Isolation

