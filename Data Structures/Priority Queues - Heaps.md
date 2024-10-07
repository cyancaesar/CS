### Heap (Priority Queue)

- A new ADT
- Operations:
	- Insert
	- DeleteMin

##### Priority Queue ADT

- PQueue data: collection of data with priority
- PQueue operations: insert, deleteMin
- PQueue Property
	- For two elements x and y, if *x has a lower priority value than y*, then *delete x before y*

Potential Implementations with average case:

|      ADT      | insert | deleteMin |
|:-------------:|:------:|:---------:|
| Unsorted list |  O(1)  |   O(n)    |
|  Sorted list  |  O(n)  |   O(1)    |


##### Heap Properties

- Structure Property
- Ordering Property

**Structure Property**
- A binary heap is a complete binary tree
- Exception that is is possible to be balanced and filled from left to right at the deepest level

**Ordering Property**
- Min-Heap (Default)
- Max-Heap

##### Min-Heap

- Every node holds a key
- The key of every node must be <= the keys of the children

##### Max-Heap

- Same as Min-Heap
- But the key every node must be >= the keys of the children

##### Heap as an Array

- Numbering the nodes in the heap from top to bottom and on each level from left to right
- Array of heap has two attributes
	- Length: number of elements in the array
	- Heap-size: number of heap elements stored in the array
- Parent: `k/2`
- Left child: `i*2`
- Right child: `i*2+1`

##### Height of a Heap

- The height of an n-element heap based on a binary tree is **Log n**
- Basic operations on heaps takes **O(Log n)**

**Applications of Heaps**
- A heap implements a priority queue.
- Heap is used in sorting

---

##### Heaps Operations

- FindMin
- Insert: percolate up
- DeleteMin: percolate down


##### DeleteMin in Min-Heaps

The minimum value in a min-heap is at root

Algorithm:
1. Remove root
2. Swap **last** leaf node at root
3. Find smallest child of node
4. Swap node with its smallest child
5. Repeat steps 3 & 4 until no swaps needes

```text
If lastNode "the last leaf node" is <= both children, then stop

Q: Max number of exchanges? O(Log N) - Must percolate all the way to the bottom level
```

##### Restore Heap (Heapify)

The next stage after deleteMin, to restore the structure back to its heapness.

##### Insert in Min-Heaps

Algorithm:
1. Put the key at next leaf position
2. Percolate up until no longer needed

```
Q: Max number of exchanges? O(Log N) - Must percolate all the way to the root

Average: O(1)
```

```
Exercise: Build the Heap

11 54 10 2 9 5 8 3 9 0 6 1
```