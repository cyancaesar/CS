##### Array

- Most common used data structure: **Array**
- Structures of related data items: **Array**
- Same name and type: **Array**
- `int n[2] = {1,2}`: **Initializer list**
- Must be initialized when declared: **Constants**
- Named constants or read-only variables: **Constants**
- Arrays or characters: **Strings**
- [&check;] All strings end with null ('\0')
- `char str[] = "hello"` 6 elements "null is implicitly added"
	- `char str[] = {'h', 'e', 'l', 'l', 'o', '\0'}` 
- Total memory requirement for array: `sizeof(type) * size of array`
- Multiple-Subscripted Arrays (table): **Array of arrays**

##### Pointer

- Contain memery address as their value: **Pointer variable**
- A normal variable contains a specific value: **Direct reference**
- A pointer contains an address: **Indirect reference**
- Operators used in pointers
	- `*` value of
	- `&` address of

##### Sturctures

- Individual components of a struct type are called: **members or fields**
- Members can be of different types (simple, array of struct)
- A struct is named as a whole while *individual members* are named using: **field identifiers**
- Complex data structures can be formed with: **Array of structs**
- Ordinary array: **One type of data**
- Array of structs: **Multiple types of data in each array element**

##### Linked List

- Linked list is called "linked": because each node is in the series has a pointer that links to the next node
- Each data item is: **embedded in a node**
- Each node: **has a reference to the next node**
- In a circular linked list, to know if you finished traversing: **Check if the pointer of the current node is equal to the head**

##### Stack and Queue

- A stack is an ordered group of *homogeneous* items, in which the removal and addition of stacks items only at the top of the stack
- A LIFO "Last In, First Out" structure for stack
- Primary operation: **push** and **pop**
- Auxiliary operation: **top**, **size**, **isEmpty** and **isFull**
- Bottom of the stack is at location **0**, then an empty stack has top of **-1**
- For pushing item, *increment top and store item at stk[top]*
- For popping item, *get the item at stk[top] and decrement top*
- Postfix expression *does not require any precedence rules*

- A FIFO "First In, First Out" structure for queue
- In queue, *insertion is done at one end and deletion is done at other end*
- Primary operation: **enqueue** and **dequeue**
	- Enqueue: insert element front rear
	- Dequeue: delete element from front