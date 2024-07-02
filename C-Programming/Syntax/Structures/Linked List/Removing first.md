To pop a variable, we will need to reverse this action:

1. Take the next item that the head points to and save it
2. Free the head item
3. Set the head to be the next item that we've stored on the side

Here is the code:

```c
int pop(node_t ** head) {
    int retval = -1;
    node_t * next_node = NULL;

    if (*head == NULL) {
        return -1;
    }

    next_node = (*head)->next;
    retval = (*head)->val;
    free(*head);
    *head = next_node;

    return retval;
}
```