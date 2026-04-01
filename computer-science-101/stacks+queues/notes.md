### Stacks and Queues
- Both stacks and queues are O(1) runtime because we don't have to worry about getting ot the middle of the array or list, only the ends of the data. 

  - Note: This does require a doubly linked list with a tail pointer

### Stacks - LIFO - Last in First Out

- all items with stack operations are O(1) or constant time
- _pop_ to get and remove the TOP element of a stack
- _push_ to add something to the stack

Examples of a stack
  - Undo/redo 
     - when we undo/redo there are 2 stacks holding values. If we choose to add something that isn't a redo we actually clear the redo stack complexity and only keep values in the undo stack and continue as normal. 
    - if you reach a spot where you can no longer undo it is because the stack id full and cannot give any additional values. 
  - Maze
    - values are added to the stack as they are visited, and are removed if a dead end is reached

```sh
//array
class Stack {
    constructor() { this.items = []; }

    // Push operation
    push(element) { this.items.push(element); }

    // Pop operation
    pop()
    {
        if (this.isEmpty()) {
            return "Stack is empty";
        }
        return this.items.pop();
    }

    // Peek operation
    peek()
    {
        if (this.isEmpty()) {
            return "Stack is empty";
        }
        return this.items[this.items.length - 1];
    }

    // isEmpty operation
    isEmpty() { return this.items.length === 0; }

    // Size operation
    size() { return this.items.length; }

    // Print the stack
    print() { console.log(this.items); }
}

// Example Usage
const stack = new Stack();

stack.push(10);
stack.push(20);
stack.push(30);
console.log(stack.peek());
console.log(stack.pop());
console.log(stack.size());
console.log(stack.isEmpty());
stack.print();
```

```sh
//linked list
// Node class representing each element in the stack
class Node {
    constructor(value)
    {
        this.value = value;
        this.next = null;
    }
}

// Stack class using a Linked List
class Stack {
    constructor()
    {
        this.top = null;
        this.size = 0;
    }

    // Push operation
    push(value)
    {
        const newNode = new Node(value);
        newNode.next = this.top;
        this.top = newNode;
        this.size++;
    }

    // Pop operation
    pop()
    {
        if (this.isEmpty()) {
            console.log("Stack is empty!");
            return null;
        }
        const poppedValue = this.top.value;
        this.top = this.top.next;
        this.size--;
        return poppedValue;
    }

    // Peek operation
    peek()
    {
        return this.isEmpty() ? null : this.top.value;
    }

    // Check if the stack is empty
    isEmpty() { return this.size === 0; }

    // Returns the size of the stack
    getSize() { return this.size; }

    // Print stack elements
    printStack()
    {
        let current = this.top;
        let stackValues = [];
        while (current) {
            stackValues.push(current.value);
            current = current.next;
        }
        console.log("Stack:", stackValues.join(" -> "));
    }
}

// Example Usage
const stack = new Stack();
stack.push(10);
stack.push(20);
stack.push(30);
stack.printStack();
console.log("Top Element:", stack.peek());
console.log("Popped Element:", stack.pop());
stack.printStack();
```

### Queues - FIFO - First in First Out
- Used when you want all of the items to have the same amount of value and you want the value that has been waiting the longest to get served First
- Queues can only be used with doubly linked lists using a tail pointer
- _enqueue_ to insert an element into a queue
- _dequeue_ to remove an element from a queue

Examples of a queue
  - Scheduling for a computer 
    - Printing for multiple user computer on one printer. The printer will print in the order the job is added.

```sh
//array
class Queue {
  constructor() {
    this.items = [];
  }

  enqueue(element) {
    this.items.push(element); 
  }

  dequeue() {
    return this.isEmpty() ? "Queue is empty" : this.items.shift();
  }

  peek() {
    return this.isEmpty() ? "Queue is empty" : this.items[0];
  }

  isEmpty() {
    return this.items.length === 0;
  }

  size() {
    return this.items.length;
  }

  print() {
    console.log(this.items.join(" -> "));
  }
}

// Example usage:
const queue = new Queue();
queue.enqueue(1);
queue.enqueue(2);
queue.enqueue(3);
queue.print();
console.log(queue.dequeue());
console.log(queue.peek()); 
console.log(queue.size());
```

```sh
//Linked List
class Node {
    constructor(data) {
        this.data = data;
        this.next = null;
    }
}

class Queue {
    constructor() {
        this.front = null;  
        this.rear = null; 
        this.size = 0; 
    }
    enqueue(data) {
        const newNode = new Node(data);
        if (this.isEmpty()) {
            this.front = newNode;
            this.rear = newNode;
        } else {
            this.rear.next = newNode;
            this.rear = newNode;
        }
        this.size++;
    }
    dequeue() {
        if (this.isEmpty()) {
            return null; 
        }
        const removedNode = this.front;
        this.front = this.front.next;
        if (this.front === null) {
            this.rear = null;
        }
        this.size--;
        return removedNode.data;
    }
    peek() {
        if (this.isEmpty()) {
            return null;
        }
        return this.front.data;
    }
    isEmpty() {
        return this.size === 0;
    }
    getSize() {
        return this.size;
    }
    print() {
        let current = this.front;
        const elements = [];
        while (current) {
            elements.push(current.data);
            current = current.next;
        }
        console.log(elements.join(' -> '));
    }
}

// Example Usage:
const queue = new Queue();
queue.enqueue(10);
queue.enqueue(20);
queue.enqueue(30);
queue.print(); 

console.log(queue.dequeue());
queue.print();

console.log(queue.peek()); 
console.log(queue.getSize());
console.log(queue.isEmpty());
```