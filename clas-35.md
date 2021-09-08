# Graphs 

***A graph is a non-linear data structure that can be looked at as a collection of vertices (or nodes) potentially connected by line segments named edges.***

**Here is some common terminology used when working with Graphs:**

* Vertex : 

*A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.*
    
* Edge : 

*An edge is a connection between two nodes.*

* Neighbor : 

*The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.*

* Degree : 

*The degree of a vertex is the number of edges connected to that vertex.*

## Directed vs Undirected 

> Undirected Graphs 

**An Undirected Graph is a graph where each edge is undirected or bi-directional. This means that the undirected graph does not move in any direction.**

*For example, in the graph below, Node C is connected to Node A, Node E and Node B. There are no “directions” given to point to specific vertices. The connection is bi-directional.*

![Example](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/UndirectedGraph.PNG)

*The undirected graph we are looking at has 6 vertices and 7 undirected edges.*

*Vertices/Nodes = {a,b,c,d,e,f}*

*Edges = {(a,c),(a,d),(b,c),(b,f),(c,e),(d,e),(e,f)}*

> Directed Graphs (Digraph) 

**A Directed Graph also called a Digraph is a graph where every edge is directed.**

**a Digraph has direction. Each node is directed at another node with a specific requirement of what node should be referenced next.**

![Example2](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/DirectedGraph.PNG)

*The directed graph above has six vertices and eight directed edges*

*Vertices = {a,b,c,d,e,f}*

*Edges = {(a,c),(b,c),(b,f),(c,e),(d,a),(d,e)(e,c)(e,f)}*

## Complete vs Connected vs Disconnected 

> Complete Graphs 

**A complete graph is when all nodes are connected to all other nodes.**

![Example3](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/CompleteGraph.PNG)

> Connected 

**A connected graph is graph that has all of vertices/nodes have at least one edge.**

![Example4](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/ConnectedGraph.PNG)

> Disconnected 

**A disconnected graph is a graph where some vertices may not have edges.**

![Example5](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/DisconnectedGraph.PNG)

## Acyclic vs Cyclic 

> Acyclic Graph 

**An acyclic graph is a directed graph without cycles.**

**A cycle is when a node can be traversed through and potentially end up back at itself.**

![Example6](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/threeAcyclic.png)

> Cyclic Graphs 

**A Cyclic graph is a graph that has cycles.**

**A cycle is defined as a path of a positive length that starts and ends at the same vertex.**

![Example7](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/cyclic.PNG)

## Graph Representation 

> Adjacency Matrix 

**An Adjacency matrix is represented through a 2-dimensional array. If there are n vertices, then we are looking at an n x n Boolean matrix**

![Example8](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/AdjMatrix.PNG)

***a sparse graph is when there are very few connections.*** 

***a dense graph is when there are many connections.***

***Within an adjacency matrix, an undirected graph will always be symmetric. This is not the case for a directed graph.***

> Adjacency List 

***An adjacency list is the most common way to represent graphs.***

***An adjacency list is a collection of linked lists or array that lists all of the other vertices that are connected.***

![Example9](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/AdjList.PNG)

## Weighted Graphs 

**A weighted graph is a graph with numbers assigned to its edges. These numbers are called weights.**

![Example10](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/weightGraph.PNG)

> weight matrix 

![Example11](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/weightMatrix.PNG)

> weight lists

![Example12](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/weightList.PNG)

## Traversals 

> Breadth First 

**Breadth first traversal is when you visit all the nodes that are closest to the root as possible. From there you traverse outwards, level by level, until you have visited all the vertices/nodes.**

*Here is what the algorithm breadth first traversal looks like:*

1. Enqueue the declared start node into the Queue.
2. Create a loop that will run while the node still has nodes present.
3. Dequeue the first node from the queue
4. if the Dequeue‘d node has unvisited child nodes, add the unvisited children to visited set and insert them into the queue.

![Example12](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/BreadthFirst.PNG)

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

> Depth First 

**In a depth first traversal, we approach it a bit different than the way we do when working with a depth first traversal of a tree. Similar to how the breadth-first uses a queue, we are going to use a Stack for our depth-first traversal.**

*The algorithm for a depth first traversal is as follows:*

1. Push the root node into the stack
2. Start a while loop while the stack is not empty
3. Peek at the top node in the stack
4. If the top node has unvisited children, mark the top node as visited, and then Push any unvisited children back into the stack.
5. If the top node does not have any unvisited children, Pop that node off the stack
6. repeat until the stack is empty.

![Example13](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/Depth1.PNG)

## Real World Uses of Graphs 

1. GPS and Mapping
2. Driving Directions
3. Social Networks
4. Airline Traffic
5. Netflix uses graphs for suggestions of products