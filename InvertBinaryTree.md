# Invert a binary tree in JavaScript

## Runtime: 

## Given a tree made of nodes in the form:
```JS
function Node(value, left, right) {
  this.value = value;
  this.left = left ? left : null;
  this.right = right ? right : null;
}
```
## Invert the tree such that each left child is swapped with each right child

### Steps:
```pseudo
  1. Set the left node to a temp variable
  2. Set the left node equal to the right node
  3. Set the right node equal to the temp variable
  4. Recursively call the function on the left node until there are no more left nodes
  5. Recursively call the function on the right nodes until there are no more right nodes
  6. Return the tree
```
### JavaScript Implementation:
## Iterative:
```JS
function invertTree(node) {
  if (!node || !node.left || !node.right) {
    return node;
  }
  let temp = node.left;
  let node.left = node.right;
  let node.right = temp;
  invertTree(node.left);
  invertTree(node.right);
  return node;
}
```

Source: https://stackoverflow.com/questions/62954565/how-can-i-invert-a-binary-tree-in-javascript
  
