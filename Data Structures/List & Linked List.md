**List Types:**
- Single Linked List
- Double Linked List
- Circular Linked List

Two built-in data structure that can be used to implement ANOTHER data structure
- Arrays
- List

List is an ordered set of data, which can be used to store objects and processed sequentially.

On the other hand, Arrays is an indexed set of member.

List is a set of item, while Array is a set of variables that each store an item.

Disadvantage of Array as a storage data structure:
- Slow search in unorder array. (If ordered binary search can be useful)
- Slow insertion in ordered array.
- Fixed size

Array has fixed length, while list can be extended during the run-time.

Linked List is a general-purpose storage data structure.

---

**Linked List** is a series of connected nodes.
Each node contain at least:
- A data
- A pointer to the next node

Example of minimal node:

```cpp
struct Node
{
	int data; // data to store
	Node* next_node; // pointer to next node
};
```

Example of extended node:

```cpp
struct Node
{
	int real_number;
	int complex_number;
	Node* next_node;
};
```

The extended node contains two data to store and one pointer variable which is mandatory.

**Head** is a pointer to the first node.
**Last node** points to NULL value.

Linked List Charactaristics:
- Each item/data is embedded inside its node
- Each node contains a reference/pointer to the next node
- In Array, each item/data is indexed. So accessing the item by its position/index `O(1)`.
- While Linked List, the only way to access the desired data is by traversing the list from the head `O(n)`.

**Linked List Insertions**
- Insertion at the top
- Insertion at the bottom
- Insertion at the middle

Implementation of Linked List Insertions:

```cpp
void insert_first(int _data)
{
	struct Node* new_node = new Node();
	struct Node* current_node = head;
	new_node->data = _data;

	if (!head)
		head = new_node;

	new_node->next = current_node;
	head = new_node;
}
```
```cpp
void insert_last(int _data)
{
	struct Node* new_node = new Node();
	struct Node* current_node = head;
	new_node->data = _data;
	new_node->next = NULL;

	if (head == NULL)
	{
		head = new_node;
		return;
	}
	
	while (current_node->next != NULL)
	{
		current_node = current_node->next;
	}

	current_node->next = new_node;
}
```
```cpp
void insert_middle(int _data)
{
	struct Node* new_node = new Node();
	struct Node* current_node = head;
	struct Node* prev_node = NULL;
	int size = 0;

	new_node->data = _data;

	while (current_node != NULL)
	{
		current_node = current_node->next;
		size++;
	}
	current_node = head;

	for (int i = 0; i <= (size / 2); i++)
	{
		prev_node = current_node;
		current_node = current_node->next;
	}
	prev_node->next = new_node;
	new_node->next = current_node;
}
```

---

**Circular Linked Lists**

The last node points to the head/first node.

To check if you have finished traversing the whole list, compare the current pointer with the head node.

**Doubly Linked Lists**

- Each node points forward and backward.
- There are two NULL, the first node points back with NULL, the last node points forward with NULL

Advantage of Doubly Linked Lists is that it is easy to navigate back.

**Summary of advantage of Linked List:**
- Dynamic
- Easy and fast insertion and deletions
	- To insert or delete in array context, we make temporary variable to make room for new element or to close the gap caused by deleted elements
	- With linked list, no need to move other nodes. Only need to reset some pointers

**Comparison**

- Size
	- Increase the size of a resizable array can waste storage and time
- Storage requirements
	- Array-based require less memory than a pointer-based ones
- Access time
	- Array-based: constant access time `O(1)`
	- Pointer-based: `O(n)`
- Insertion and deletions
	- Array-based: require shifting of data
	- Pointer-based: require a list traversal

Deletion in doubly linked list:
```cpp
(curr->prev)->next = curr->next;
(curr->next)->back = curr->back;
```

Insertion in doubly linked list:
```cpp
new_node->next = curr;
new_node->back = curr->back;
curr->back = curr;
new_node->back->next = new_node;
```

