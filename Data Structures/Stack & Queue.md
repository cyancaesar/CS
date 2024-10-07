Stack is LIFO (Last-in First-out)

Stack can be implemented with
- Array (Static)
- Linked List (Dynamic)

Main Stack Operation:
- push
- pop

Auxiliary Stack Operation
- top/peak
- isEmpty
- isFull
- size

---

Queue like stack, is also a list.
Insertion is performed in one end while deletion is performed in other end.

Queue is FIFO (First-in First-out)

Queue Operation:
- Enqueue
- Dequeue

Enqueue insertion is inserted on rear
Dequeue deletion is deleted on front

![[Pasted image 20221003102932.png]]

front is always fixed, while rear acts as an index.

---

### Final Notes

##### Evaluation of Postfix Expressions

- When an operand is encountered, push it to stack
- When an operator is encountered
	- Pops the operands two times
	- Push the result of the operation on the stack

##### Infix to Postfix Conversion

- Operands: add to expression/screen
- Close parenthesis: pop stack symbols until an open parenthesis appears
- Operator: Pop all stack symbols until a symbol of lower precedence appears. Then push the operator
- End of input: Pop all remaining stack symbols and add to the expression
