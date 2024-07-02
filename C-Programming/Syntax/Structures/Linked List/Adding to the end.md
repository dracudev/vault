To iterate over all the members of the linked list, we use a pointer called `current`. We set it to start from the head and then in each step, we advance the pointer to the next item in the list, until we reach the last item.

```c
void push(node_t * head, int val) {
    node_t * current = head;
    while (current->next != NULL) {
        current = current->next;
    }

    /* now we can add a new variable */
    current->next = (node_t *) malloc(sizeof(node_t));
    current->next->val = val;
    current->next->next = NULL;
}
```