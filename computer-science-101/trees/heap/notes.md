### Heap
- Subdivision of a tree

- A tree with an additional property.

- A parent node is going to have a significant relationship with each of its children nodes: Greater than or less than

- If er go any line up the heap its going to go in ascending order. The bottom of the tree is going to be lowe than every single point going back up the tree

- At the very top is alway going to be the max of the data structure. 

_Binary heap_ - filling the tree with nodes evenly  
  - with every insertion we have to look at our values to make sure we are not violating the node with its parent until we are no longer violating our heap Rules
  
Runtime: 
  - Insert - O(logn) 
  
  - Check max or min - O(1) constant time bc the root number is always the greatest number 

  - Remove max/min - O(logn)

  Real World Examples
    - Priority queues (allows you to give weight to values and prioritize them over other values)
    - Dijkstra's Algorithm - used to find the least amount of moves to get from one node to the next (shortest path)