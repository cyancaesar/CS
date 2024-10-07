## Tree

- Each node can have 0 or more children
- A node can have at most one parent

### Binary Tree

- Tree with 0-2 children per node

- Root: no parent
- Interior: non-leaf
- Leaf: no child
- Height: distance from root to deepest leaf

### Binary Search Tree

**Key Property**

Value at node
- Smaller values in left subtree
- Larger values in right subtree

### Types of Binary Tree

- Degenerate   : only one child 
- Complete      : always two children
- Balanced       : mostly two children

**Binary Tree Properties**
- Degenerate
	- O(n)
	- Linked List like
- Balanced
	- O(log n)
	- Search effecient

### Binary Search Tree: Insertion

1. Search for value X
2. Search will end at node Y (if X not in tree)
3. If X < Y, insert new leaf X as new left subtree for Y
4. If X > Y, insert new leaf X as new right subtree for Y

- O(log n) for balanced tree
- May unbalance tree

### Binary Search Tree: Deletion

1. Search for value X
2. If X is a leaf, delete X
3. If X is not a leaf
	1. Replace with largest value Y on left subtree **OR** smallest value Z on right subtree
	2. Delete replacement value (Y or Z) from subtree

- O(log n) for balanced tree
- May unbalance tree

**Example**
Delete by finding largest value on left subtree:

![[Tree-1668585769557.jpeg|225]]
![[Tree-1668585851782.jpeg|225]]
![[Tree-1668585876944.jpeg|225]]

Delete by finding smallest value on right subtree:

![[Tree-1668585948580.jpeg|225]]
![[Tree-1668585967875.jpeg|225]]
![[Tree-1668585978936.jpeg|225]]

### Non-binary search tree

- 2-3 tree
	- Each internal node has 2 or 3 children
	- All leaves at same depth (height balanced)
- B-trees
	- Generalization of 2-3 trees
	- Each internal node has between k/2 and k children
	- Widely used in databases
- **Parse trees**
	- Convert from textual representation to tree representation
	- Textual program to tree (used in compilers)
	- Tree representation of data
		- DOM
		- XML
	- Arithemtic Expression Tree parsing

### Tree Traversal: Orders

- Preorder
	- Visit root
	- Visit left subtree
	- Vist right subtree
- Inorder
	- Visit left subtree
	- Visit root
	- Visit right subtree
- Postorder
	- Visit left subtree
	- Visit right subtree
	- Visit root


##### Inorder

```cpp
void inOrder()
{
	if (left != NULL) cout << left->inOrder();
	cout << data;
	if (right != NULL) cout << right->inOrder();
}
void preOrder()
{
	cout << data;
	if (left != NULL) cout << left->inOrder();
	if (right != NULL) cout << right->inOrder();
}
void postOrder()
{
	if (left != NULL) cout << left->inOrder();
	if (right != NULL) cout << right->inOrder();
	cout << data;
}
```

![[Tree-1668587842825.jpeg|225]]

```
Inorder   : A - (C/5*2) + (D*5) % 4
Preorder  : + - A * / C 5 2 % * D 5 4
Postorder : A C 5 / 2 * - D 5 * 4 % +
```

![[Tree-1668588101422.jpeg|225]]

```
Inorder   : 4 5 6 3 1 8 7 9 11 10 12
Preorder  : 1 3 5 4 6 7 8 9 10 11 12
Postorder : 4 6 5 3 8 11 12 10 9 7 1
```

![[Tree-1668588291719.jpeg|225]]

```
Inorder   : <PRACTICE>
Preorder  : <PRACTICE>
Postorder : <PRACTICE>
```

![[Tree-1668588908144.jpeg|350]]

![[Tree-1668588924837.jpeg|425]]

### Array Representation of Complete Trees & Balanced Tree

- Parent of current node: k/2
- Left child : k\*2
- Right child : k\*2+1

