---
layout: post
title: "Problems on Stack, Queues and Linked Lists"
description: "Problems"
date: 2016-12-22
tags: [algorithm, stack, queues, linked list, data structures, problems]
comments: true
share: true
---
### Question

There is a stream of numbers. At any instant you need to output last n numbers which appeared in the stream.

Think about it before looking at the solution.

**Solution:** Maintain a queue of size n, and as the numbers keep on coming, keeping on pushing them to queue until queue is full. Now as the queue is full, the queue will have n elements.

Now as the numbers keep on coming, keep popping elements from the front end and pushing the new element from the rear end. Its like a pipe which has capacity of n elements.

This way you will maintain last n elements in the queue.




### Question

Given a sequence of opening and closing braces, find whether the given sequence is a valid sequence or not. e.g. ((())) - valid,  (()()) - valid, ()()(  - invalid

**Solution:** This problem can be solved by using stack. Following is the algorithm:

* Traverse over the string, on encounter with '(' push it to the stack
* On encounter with ')' pop from the stack
* After having finished with the traversal, check if the stack is empty or not - if its empty - the given sequence is valid, if not empty - its invalid
For complete working code go to :

[BracketValidationCode](https://github.com/dummybyte/CodeBlog/blob/master/BracketValidation.cpp)


### Question

Given a linked list, reverse it.

* **Input:** head of the linked list to be reversed
* **Output:** head of the reverse linked list

**Solution:** Following is the algorithm: (3 pointers method)

* if there is single node or no node then return that node
* if there is two nodes then reverse those nodes and return the newHead
* if there are more nodes then:
* we will maintain 3 pointers namely- previous, current and newHead such that ```current = previous->next;``` and ```newHead = current->next;``` initially
* Now for each iteration of the loop, we will be reversing only current and previous nodes and this will result into breaking of linked list into two linked lists whose one head is current and other head is newHead after each iteration of the while loop.
* We just need to connect current and newHead each time

For the detail working code please see:

[Reverse Linked List](https://github.com/dummybyte/CodeBlog/blob/master/ReverseLinkedList.cpp)


### Question
Clone a linked list with next and a random pointer

* **Input** head of linked list to be cloned
* **Output** head of the clone linked list

**Solution:** The solution would here be trivial if the given linked list didn't have the random pointer.
To solve this problem, lets see at following steps:

* First of all, we will insert nodes between all the two nodes of the given linked list such that
```
    newNode->next = oldNode->next;
    oldNode->next = newNode;
```

* One node we need to insert either at the beginning or at the end (we will insert at the end)

* Now we need to define the next and the random pointers for the newly inserted nodes
```
    newNode->next = oldNode->next->next;
    newNode->randomPtr = oldNode->randomPtr->next;
```

* Insert a node at the last node and configure it accordingly
For the full working code, see the following link:

[Clone Linked List with random ptr](https://github.com/dummybyte/CodeBlog/blob/master/CloneLinkedListRndPtr.cpp)
