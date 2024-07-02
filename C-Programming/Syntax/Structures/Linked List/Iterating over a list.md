Let's build a function that prints out all the items of a list. To do this, we need to use a `current` pointer that will keep track of the node we are currently printing. After printing the value of the node, we set the `current` pointer to the next node, and print again, until we've reached the end of the list (the next node is NULL).

```c
void print_list(node_t * head) {
    node_t * current = head;

    while (current != NULL) {
        printf("%d\n", current->val);
        current = current->next;
    }
}
```