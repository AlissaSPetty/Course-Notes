### Binary Search Tree (BST)

_binary_ - two options

_search_ - search through nodes to get to data quicker

_tree_ - uses tree properties

- Always compares the root node and moves values to right if greater than and left if less than

- If a BST is always one split to the right or left then we cannot search as easily and this becomes a linked list. 

  | Operation | Average | Worst | 
  | --- | --- | --- |
  | Search | O(logn) | O(n) |
  | Insert | O(logn) | O(n) |
  | Delete | O(logn) | O(n) |

1. Create node function 
2. Create a base case because function is using recursion
3. create if/else for the tree traversal (left for less than and right for greater than)

BST Rules: 
  1. Each node can have at most 2 children
  2. All right children must be greater than 
  3. All left children must be less than or equal to 