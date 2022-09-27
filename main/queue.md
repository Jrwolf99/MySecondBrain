---
tags:
- programming
---
# queue

queue is a data structure (see [[data structures]]).

#### the data structure 
uses FIFO (First In First Out).

![[Pasted image 20220924153053.png]]

**Enqueue**: someone walks up to the end of the line.
**Dequeue**: someone is at the front of the line and gets to "go into the club".
**isEmpty**: returns true if queue is empty
**Top**: returns the first element of the queue.




#### code example

* in Java, a "java.util.Queue" is a subtype of the java.util.Collection interface.
* most commonly, Queue implementations are LinkedLists, ArrayBlockingQueue, and PriorityQueue.

```java
	Queue<String> queue = new LinkedList<>();
```

#### resources