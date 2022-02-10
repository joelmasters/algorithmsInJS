# Reverse and Linked List implementation in JavaScript

## Runtime: O(n)

## Given a linked list in the form:
```JS
function Node(value) {
  this.value = value;
  this.next = null;
}
```
## Reverse the list such that the function takes as an argument the existing head node in the list and returns the new head node

### Steps:
```pseudo
  1. Iterate through the list once
  2. At each node, perform the following operations in order:
    a. Store the next node in a temp node
    b. Set the next node node equal to the previous node
    c. Set the previous node equal to the current node
    d. Set the current node equal to the temp node (step forward)
  8. if the start index has crossed over the end index (start > end), the value we are looking for is not in the array
    9. return -1
```
### JavaScript Implementation:
## Iterative:
```JS
function reverse(head) {
  let node = head;
  let previous;
  let temp;
  
  while (node) {
    temp = node.next;
    node.next = previous;
    previous = node;
    node = temp;
  }
  return previous;
}
```

## Recursive:
```JS
function reverse(head) {
  if (!head || !head.next) {
    return head;
  }
  let temp = reverse(head.next);
  head.next.next = head;
  head.next = undefined;
  return temp;
}
```

Source: https://wsvincent.com/javascript-reverse-linked-list/
  
