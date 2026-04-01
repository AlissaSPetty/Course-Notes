### Linked Lists
* allow us to maintain our list by adding only one node to the chain, no more and no less. 

* linked lists are better for front insertions, and arrays are better for back insertions

* We sacrifice time for memory, which is more useful in larger data sets.

* _Node_ - Locational object or object that references other objects. They have the ability to connect to each other

* adding a new node always include the mode being linked to NULL before adding it to the linked list

* it is easier to link to the front of a linked list by reassigning the head and using O(1) runtime

* Real World Examples: 
  - trees, queues, data storage
  - when defragmenting a computer you reorg fragmented filed on your hard drive to improve performance and speed, which is made when a computer creates a linked list to quickly store large files in the hard drive
  - back and forward buttons in a web browser

#### Singly Linked Lists
* Allows you to connect data all over the place together and allows you to add on to the linked list without dealing with expanding an array

Time Complexity for Singly Linked List: 
* _To Insert randomly into a Linked List_ - O(n) or linear time
* _To Insert into the Front of a Linked List_ -  O(1) or constant time
* _To Insert into the Back of a Linked List_ -  O(n) or linear time

* _To Delete the Front Node of a Linked List_ -  O(n) or linear time - delete head, reassign head, then use variable to delete original head
* _To Delete the Back Node of a Linked List_ -  O(n) or linear time - take next to last node, set it equal to null, then use var to delete the last node

Does not matter if sorted or not, always O(n) because we have to traverse the entire list in the worst case
* _To Search a Sorted Linked List_ - O(n)

* _To Search an Unsorted Linked List_ - O(n) 

To create an initial linked list
1. create a new node class, give it a constructor (value), 
  - set `new Node = this.value`
  - set `this.next = null`
2. create a linked list function 
  - set `this.head = null`
  - append the value by using `let new Node = nee Node(value)`
3. check if the head is null `!this.head`
  - if so we set the head to our new Node value
4. create a new variable `let current = this.head `
  - `while (current.next) {current = current.next} current.next = new Node`

To create a new node and add it to the beginning of the linked list:
  1. Create the node and put it in the data
  2. Make the next of the new node the head value
  3. Move the head to point to the new node.

```sh
class Node{
    constructor(value)
    {
    this.value=value
    this.next=null
    }
}
class LinkedList{
    constructor()
    {
        this.head=null
    }
    append(value)
    {
        let newnode=new Node(value)
        if(!this.head)
        {
            this.head=newnode
            return
        }
        let current=this.head
        while(current.next)
        {
            current=current.next
        }
        current.next=newnode
        
    }
    printList(){
      let current=this.head
      let result=""
      while(current)
      {
          result+=current.value+'->'
          current=current.next
      }
      console.log(result+'null')
    }
}
let list=new LinkedList()
list.append(10)
list.append(20)
list.append(30)
list.printList()
```

#### Doubly Linked Lists
* Instead of linking only to the next node in a list we can also link to the previous node.

* This does not help much with runtimes, but it helps add to the end of a list. 

* _Tail Pointer_ - allows us to keep track of what is the last node - adds one extra operation to add add to the end, but also allows us to insert to the back in constant time n(1). 

```sh
class Node {
    constructor(data){
        // To store the value or data.
        this.data = data;

        // Reference to the previous node
        this.prev = null;

        // Reference to the next node
        this.next = null;
    }
}

class Node {
    constructor(value) {
        this.data = value;
        this.prev = null;
        this.next = null;
    }
}

// Driver Code
// Create the first node (head of the list)
let head = new Node(10);

// Create and link the second node
head.next = new Node(20);
head.next.prev = head;

// Create and link the third node
head.next.next = new Node(30);
head.next.next.prev = head.next;

// Create and link the fourth node
head.next.next.next = new Node(40);
head.next.next.next.prev = head.next.next;

// Traverse the list forward and print elements
let temp = head;
let output = "";
while (temp !== null) {
    output += temp.data;
    if (temp.next !== null) {
        output += " <-> ";
    }
    temp = temp.next;
}

console.log(output);
```