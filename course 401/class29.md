# Graphs

*A graph is a non-linear data structure that can be looked at as a collection of vertices potentially connected by line segments named edges.*

## Graph Contents: 

- Vertex - A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.
- Edge - An edge is a connection between two nodes.
- Neighbor - The neighbors of a node are its adjacent nodes.
- Degree - The degree of a vertex is the number of edges connected to that vertex.

## Directed vs Undirected

**Undirected Graph:** An Undirected Graph is a graph where each edge is undirected or bi-directional. 

The undirected graph we are looking at has 6 vertices and 7 undirected edges.

Undirected graph visual example:

![graph1](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/UndirectedGraph.PNG)

`Vertices/Nodes = {a,b,c,d,e,f}`

`Edges = {(a,c),(a,d),(b,c),(b,f),(c,e),(d,e),(e,f)}`

**Directed Graphs:**  A Directed Graph also called a Digraph is a graph where every edge is directed.


Direcyed graph visual example:

![graph2](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/DirectedGraph.PNG)

`Vertices = {a,b,c,d,e,f}`

`Edges = {(a,c),(b,c),(b,f),(c,e),(d,a),(d,e)(e,c)(e,f)}`

## Complete vs Connected vs Disconnected

### Complete Graphs

A complete graph is when all nodes are connected to all other nodes.

![cg](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/CompleteGraph.PNG)

### Connected Graphs

A connected graph is graph that has all of vertices/nodes have at least one edge.

![cog](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/ConnectedGraph.PNG)

### Disconnected Graphs

A disconnected graph is a graph where some vertices may not have edges.


![graph3](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/DisconnectedGraph.PNG)

## Acyclic vs Cyclic Graphs

### Acyclic Graph
An acyclic graph is a directed graph without cycles.

A cycle is when a node can be traversed through and potentially end up back at itself.

![Acyclic](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/threeAcyclic.png)


### Cyclic Graphs
A Cyclic graph is a graph that has cycles.

![cyclic](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/cyclic.PNG)

## Graph Representation

1. Adjacency Matrix
2. Adjacency List

### Adjacency Matrix

*An Adjacency matrix is represented through a 2-dimensional array. If there are n vertices, then we are looking at an n x n Boolean matrix*

![adjacent](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/AdjMatrix.PNG)

*A few things to note from the above:*

- Looking at the graph we are representing, you can see that Vertex A connects to both Vertex D and Vertex C. 
- We follow this same pattern for the other vertex’s and where they are connected.

### Adjacency List

*An adjacency list is the most common way to represent graphs.*

![list](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/AdjList.PNG)

**Code Implementation:**

- We can visually see that we are working with a collection of some sort. The visual is depicting a Linked List, but you could easily make it an array of arrays if you’d like.
- Each index or node (depending on the data structure you choose to represent the adjacency list) will be a vertex within the graph.
- Every time you add an edge, you will find the appropriate vertices in the data structure and add it to the appropriate location.


## Weighted Graphs

A weighted graph is a graph with numbers assigned to its edges. These numbers are called weights.

![wg](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/weightGraph.PNG)

## Traversals

## Breadth First

In a breadth first traversal, you are starting at a specific vertex/node. This node must be specified when calling the BreadthFirst() method. The breadth-first traversal of a graph is like that of a tree, with the exception that graphs can have cycles.

**Algorithm:**

- Enqueue the declared start node into the Queue.
- Create a loop that will run while the node still has nodes present.
- Dequeue the first node from the queue
- if the Dequeue‘d node has unvisited child nodes, add the unvisited children to visited set and insert them into the queue.

![bfs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/BreadthFirst.PNG)

**Pseudo code:**

```
ALGORITHM BreadthFirst(vertex)
    DECLARE nodes <-- new List()
    DECLARE breadth <-- new Queue()
    DECLARE visited <-- new Set()

    breadth.Enqueue(vertex)
    visited.Add(vertex)

    while (breadth is not empty)
        DECLARE front <-- breadth.Dequeue()
        nodes.Add(front)

        for each child in front.Children
            if(child is not visited)
                visited.Add(child)
                breadth.Enqueue(child)   

    return nodes;
```

### Depth First

In a depth first traversal, we approach it a bit different than the way we do when working with a depth first traversal of a tree. 

**Algorithm:**

- Push the root node into the stack
- Start a while loop while the stack is not empty
- Peek at the top node in the stack
- If the top node has unvisited children, mark the top node as visited, and then Push any unvisited children back into the stack.
- If the top node does not have any unvisited children, Pop that node off the stack
- repeat until the stack is empty.

![depth](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/Depth1.PNG)

## Graphs Applications

1. GPS and Mapping
2. Driving Directions
3. Social Networks
4. Airline Traffic
5. Netflix uses graphs for suggestions of products





