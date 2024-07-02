A linked list is a linear data structure where each element is a separate object, called a node. Each node contains data and a reference (or link) to the next node in the sequence. If the pointer is NULL, then it is the last node in the list.

![[Pasted image 20240702104824.png]]

Linked lists have a few advantages over arrays:

1. Items can be added or removed from the middle of the list
2. There is no need to define an initial size
## Node Structure

To define a linked list node, you use a `struct` that includes data and a pointer to the next node.
```c
typedef struct s_list
{
	void			*content;
	struct s_list	*next;
}              t_list;
```

Notice that we are defining the struct in a recursive manner, which is possible in C.