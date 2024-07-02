Let's define a linked list node:

```c
typedef struct node {
    int val;
    struct node * next;
} node_t;
```

Notice that we are defining the struct in a recursive manner, which is possible in C. Let's name our node type `node_t`.

Now we can use the nodes. Let's create a local variable which points to the first item of the list (called `head`).

```c
node_t * head = NULL;
head = (node_t *) malloc(sizeof(node_t));
if (head == NULL) {
    return 1;
}

head->val = 1;
head->next = NULL;
```

We've just created the first variable in the list. We must set the value, and the next item to be empty, if we want to finish populating the list. Notice that we should always check if malloc returned a NULL value or not.

To add a variable to the end of the list, we can just continue advancing to the next pointer:

```c
node_t * head = NULL;
head = (node_t *) malloc(sizeof(node_t));
head->val = 1;
head->next = (node_t *) malloc(sizeof(node_t));
head->next->val = 2;
head->next->next = NULL;
```

This can go on and on, but what we should actually do is advance to the last item of the list, until the `next` variable will be `NULL`.