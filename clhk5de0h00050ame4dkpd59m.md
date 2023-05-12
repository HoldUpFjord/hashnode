---
title: "Implementing a Queue"
seoTitle: "Queue's, a common DS&A interview question."
seoDescription: "Queue's are a simple, yet very effective algorithm to implement. Commonplace in technical interviews, knowing how to use one is critical."
datePublished: Fri May 12 2023 05:58:12 GMT+0000 (Coordinated Universal Time)
cuid: clhk5de0h00050ame4dkpd59m
slug: implementing-a-queue
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1683866479138/bbe6d7db-2803-4afe-861f-121d8416623b.png
tags: algorithms, programming-blogs, javascript, web-development, typescript

---

## The Code:

---

```typescript
type QNode<T> = {
value:T,
next?: Node<T>,
} 

export default class Queue<T> {
//length can be modified globally
public length:number;
//head and tail can only be modified within the class Queue
private head?: Node<T>;
private tail?: Node<T>;

constructor(){
this.head = this.tail = undefined
this.length = 0
}
//add to queue
enqueue(item:T): void {
    const node = {value: item} as Node<T>;
    this.length++;
    if(!this.tail) {
        this.tail = this.head = node
        return 
    }

    this.tail.next = node;
    this.tail = node;
 }
//remove from queue
deque(): T | undefined {
//if there is no head, return undefined
    if (!this.head) {
     return undefined;
    }
    //Decrease length of list/queue
    this.length--;
    
    //declare value of head, then assign it to the following node
    const head = this.head;
    this.head = this.head.next;
    //FREE    
    this.next = undefined
    
    return head.value;
}

peek(): T | undefined {
//simple operation
//if head is not undefined, return value or return undefined
    return this.head?.value;
}
```

## What is a Queue?

---

A queue is one of the most common algorithms and is a first-in, first-out structure. It utilized Linked Lists as a data structure; if you're unfamiliar with them, here is a quick overview:

### What is a Linked List?

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683307893935/a915fa22-9542-4ac6-807e-c5ce1411a7d9.png align="center")

Some would find this description a bit reductive, but I think it's helpful to think of Linked Lists as a more primitive version of an array. Instead of each element having an index, each element, called a ***"node,"*** contains a value and a reference (or ***"pointer"***) to the next node in the list. For this example, we'll be using a singly linked list, where each node has a reference to **only** the **next node** in the list,

Practically speaking, this means that traversing a Linked List requires going through it iteratively as if you're using a for loop; whereas given an array you can access a specific value by referencing its index as seen below:

```javascript
let array = [1,2,3,4,5]

//returns 2nd index of array, value of 3
console.log(array[2])
```

---

## The 4 functions necessary in a Queue:

### Constructor

* Initialize Linked List
    
* The head and tail have the value of undefined
    
* Declare the length as zero
    

```typescript
constructor(){
this.head = this.tail = undefined
this.length = 0
}
```

### Enqueue

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683865301934/1d945653-b33f-4058-9068-9ce143edbde6.png align="center")

To add a node to a list, there are a few steps we have to do:

* Manually increase the length of our list.
    
* If there is nothing in our Linked List, our node is both the Head and the Tail.
    
* The pointer to the tail now points to the added node.
    
    * The new tail is attached to the node.
        

```javascript
enqueue(item:T): void {
    const node = {value: item} as Node<T>;
    this.length++;
    if(!this.tail) {
        this.tail = this.head = node
        return 
    }

    this.tail.next = node;
    this.tail = node;
 }
```

### Dequeue

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1683865317774/e65edac8-f5f4-454a-aca3-17652fc34934.png align="center")

A couple of steps:

* If nothing is in Linked List, return undefined
    
* Manually decrease length
    
* Declare the value of head is the next value in the list
    
    * Declare the pointer of the current header undefined
        
        * Effectively cutting off the previous node.
            

```typescript
deque(): T | undefined {
//if there is no head, return undefined
    if (!this.head) {
     return undefined;
    }
    //Decrease length of list/queue
    this.length--;
    
    //declare value of head, then assign it to the following node
    const head = this.head;
    this.head = this.head.next;
    //FREE    
    this.next = undefined
    
    return head.value;
}
```

### Peek:

Return the value of the head if it exists.

```typescript
peek(): T | undefined {
//simple operation
//if head is not undefined, return value or return undefined
    return this.head?.value;
}
```