# BREADTH-FIRST-SEARCH

```
Name         : Jackson Raj A
Register No. : 212223040071
```
<h1>ExpNo 3 : Implement Breadth First Search Traversal of a Graph</h1> 
<h3>Name:  </h3>
<h3>Register Number: </h3>
<H3>Aim:</H3>
<p>To Implement Breadth First Search Traversal of a Graph using Python 3.</p>
<h3>Theory:</h3>
<p>Breadth-First Traversal (or Search) for a graph is like the Breadth-First Traversal of a tree.
The only catch here is that, unlike trees, graphs may contain cycles so that we may come to the same node again. To avoid processing a node more than once, we divide the vertices into two categories:
<ol><li>Visited</li>
<li>Not Visited</li></ol>
</p>
<p>A Boolean visited array is used to mark the visited vertices. For simplicity, it is assumed that all vertices are reachable from the starting vertex. BFS uses a queue data structure for traversal.</p>
<p><strong>How does BFS work?</strong><br>
  Starting from the root, all the nodes at a particular level are visited first, and then the next level nodes are traversed until all the nodes are visited.
To do this, a queue is used. All the adjacent unvisited nodes of the current level are pushed into the queue, and the current-level nodes are marked visited and popped from the queue.
Illustration:
Let us understand the working of the algorithm with the help of the following example.
Step1: Initially queue and visited arrays are empty.
</p>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/8acdebf8-ecc2-4d10-a208-45cce441f059)


Queue and visited arrays are empty initially.
Step2: Push node 0 into queue and mark it visited.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/0e9ce012-8e1f-43d7-b7b9-c0fb19fe0c3f)


Push node 0 into queue and mark it visited.
Step 3: Remove node 0 from the front of queue and visit the unvisited neighbours and push them into queue.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/67d8fa3b-ce9e-46c2-9dd7-089e204e667a)

Step 4: Remove node 1 from the front of queue and visit the unvisited neighbours and push them into queue.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/b0cf0fde-8a86-41cb-a054-36875ac24ab0)

Step 5: Remove node 2 from the front of queue and visit the unvisited neighbours and push them into queue.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/8968a163-6b3a-4f7e-8ad4-bbf24f326b9b)

Step 6: Remove node 3 from the front of queue and visit the unvisited neighbours and push them into queue. 
As we can see that every neighbours of node 3 is visited, so move to the next node that are in the front of the queue.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/7a1c1b16-ea69-497f-a099-8440200f6dc0)

Steps 7: Remove node 4 from the front of queue and visit the unvisited neighbours and push them into queue. 
As we can see that every neighbours of node 4 are visited, so move to the next node that is in the front of the queue.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/8e16ffa3-c3d6-4774-822b-6eb84adedad9)

Remove node 4 from the front of queue and visit the unvisited neighbours and push them into queue.
Now, Queue becomes empty, So, terminate these process of iteration.


<hr>
<h2>Algorithm:</h2>
<hr>
<ol>
  <li>Construct a Graph with Nodes and Edges</li>
 <li>Breadth First Uses Queue and iterates through the Queue for Traversal.</li>
  <li>Insert a Start Node into the Queue.</li>
<li>Find its Successors Or neighbors and Check whether the node is visited or not.</li>
<li>If Not Visited, add it to the Queue. Else Continue.</li>
<li>Iterate steps 4 and 5 until all nodes get visited, and there are no more unvisited nodes.</li>

</ol>

## Code
```
from collections import deque, defaultdict

def bfs_graph(n, edges):
    # Create adjacency list
    graph = defaultdict(list)
    for u, v in edges:
        graph[u].append(v)
        graph[v].append(u)  # Assuming undirected graph

    # Sort adjacency lists to get consistent order
    for key in graph:
        graph[key].sort()

    # BFS
    start = edges[0][0]  # Start from first node in input
    visited = set()
    queue = deque([start])
    order = []

    while queue:
        node = queue.popleft()
        if node not in visited:
            visited.add(node)
            order.append(node)
            for neighbor in graph[node]:
                if neighbor not in visited:
                    queue.append(neighbor)
    return order

# Reading input and converting as per your format
def main():
    n, m = map(int, input().split())
    edges = [tuple(input().split()) for _ in range(m)]
    result = bfs_graph(n, edges)
    print(result)

if __name__ == "__main__":
    main()

```
<hr>
<h3>Sample Input</h3>
<hr>
7 9 <BR>
A B <BR>
A C <BR>
A F <BR>
C E <BR>
C F <BR>
C D <BR>
D E <BR>
D G <BR>
G F <BR>
<hr>
<h3>Sample Output</h3>
<hr>
['A', 'B', 'C', 'F', 'E', 'D', 'G']

<hr>

<hr>
<h3>Sample Input</h3>
<hr>
5 6 <BR>
0 1 <BR>
0 2 <BR>
1 2 <BR>
1 3 <BR>
2 4 <BR>
3 4 <BR>
<hr>
<h3>Sample Output</h3>
<hr>
['0', '1', '2', '3', '4']

## Output
<img width="1680" height="1050" alt="exp_4(1)" src="https://github.com/user-attachments/assets/8dcaa998-069a-4049-80f6-b409c473407f" />
<img width="1680" height="1050" alt="exp_4(2)" src="https://github.com/user-attachments/assets/561ebd15-6171-4105-af62-f06a52b8a3da" />

<h3>Result:</h3>
<hr>
<p>Thus,a Graph was constructed and implementation of Breadth First Search for the same graph was done successfully.</p>







