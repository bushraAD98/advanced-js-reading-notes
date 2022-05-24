# What is a graph (data structure)?

A graph is a common data structure that consists of a finite set of nodes (or vertices) and a set of edges connecting them.

A pair (x,y) is referred to as an edge, which communicates that the x vertex connects to the y vertex.



![im](https://media.geeksforgeeks.org/wp-content/cdn-uploads/undirectedgraph.png)

Graphs are used to solve real-life problems that involve representation of the problem space as a network. Examples of networks include telephone networks, circuit networks, social networks (like LinkedIn, Facebook etc.).

For example, a single user in Facebook can be represented as a node (vertex) while their connection with others can be represented as an edge between nodes.

Each node can be a structure that contains information like user’s id, name, gender, etc.

# Graph Terminology
- Adjacency: A vertex is said to be adjacent to another vertex if there is an edge connecting them. Vertices 2 and 3 are not adjacent because there is no edge between them.

- Path: A sequence of edges that allows you to go from vertex A to vertex B is called a path. 0-1, 1-2 and 0-2 are paths from vertex 0 to vertex 2.

- Directed Graph: A graph in which an edge (u,v) doesn't necessarily mean that there is an edge (v, u) as well. The edges in such a graph are represented by arrows to show the direction of the edge.

# Graph Representation

1. Adjacency Matrix
An adjacency matrix is a 2D array of V x V vertices. Each row and column represent a vertex.

If the value of any element a[i][j] is 1, it represents that there is an edge connecting vertex i and vertex j.

![img](https://cdn.programiz.com/sites/tutorial2program/files/adjacency-matrix_1.png)

Since it is an undirected graph, for edge (0,2), we also need to mark edge (2,0); making the adjacency matrix symmetric about the diagonal.

Edge lookup(checking if an edge exists between vertex A and vertex B) is extremely fast in adjacency matrix representation but we have to reserve space for every possible link between all vertices(V x V), so it requires more space.


2. Adjacency List
An adjacency list represents a graph as an array of linked lists.

The index of the array represents a vertex and each element in its linked list represents the other vertices that form an edge with the vertex.

The adjacency list for the graph we made in the first example is as follows:

![img](https://cdn.programiz.com/sites/tutorial2program/files/adjacency-list.png)


An adjacency list is efficient in terms of storage because we only need to store the values for the edges. For a graph with millions of vertices, this can mean a lot of saved space.

## Graph Operations
The most common graph operations are:

- Check if the element is present in the graph
Graph Traversal

- Add elements(vertex, edges) to graph

- Finding the path from one vertex to another

