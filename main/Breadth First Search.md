---
tags:
- programming
---
# Breadth First Search

Breadth First Search or ([BFS](https://en.wikipedia.org/wiki/Breadth-first_search)) is a [[tree]] traversal.
It has a common brother, [[Depth First Search]] (DFS).
Most common graph traversal. It can be implemented using a [[queue]].
using BFS, you start at a "root node", and then traverse the [[graph]] 

#### the [[algorithm]]
Steps:
	1. Pick a node and enqueue all its child nodes into a queue.
	2. Dequeue a node from the top of the queue, mark as visited, then enqueue all its child nodes into the queue.
	3. repeat until the queue is empty or you meed a goal. 


NOTE: the program could be stuck in infinite loop if a node is revisited and was not marked as visited before. Hence, prevent exploring nodes that are visited by marking them as visited. 

#### code example
```java
 void BFS(int s)
    {
        // Mark all the vertices as not visited(By default
        // set as false)
        boolean visited[] = new boolean[V];
 
        // Create a queue for BFS
        LinkedList<Integer> queue = new LinkedList<Integer>();
 
        // Mark the current node as visited and enqueue it
        visited[s]=true;
        queue.add(s);
 
        while (queue.size() != 0)
        {
            // Dequeue a vertex from queue and print it
            s = queue.poll();
            System.out.print(s+" ");
 
            // Get all adjacent vertices of the dequeued vertex s
            // If a adjacent has not been visited, then mark it
            // visited and enqueue it
            Iterator<Integer> i = adj[s].listIterator();
            while (i.hasNext())
            {
                int n = i.next();
                if (!visited[n])
                {
                    visited[n] = true;
                    queue.add(n);
                }
            }
        }
    }

```



![[020820_0543_BreadthFirs1.webp]]
#### resources
- https://www.educative.io/answers/what-is-breadth-first-search


