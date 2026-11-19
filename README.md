Weighted Graph Network Analysis in C
Project Overview
This project analyzes a weighted, undirected graph that represents a
network of sites and connections. Each vertex represents a site, and
each edge represents a connection with an associated cost.

The program applies Dijkstra's algorithm to find a shortest path between
a selected source and destination. It also constructs Minimum Spanning
Trees (MSTs) using Kruskal's and Prim's algorithms. Breadth-First Search
(BFS) is used to trace a path through each MST. Finally, the program
removes a selected edge and recalculates the paths to examine changes in
the network.
Table of Contents
1. Objectives
2. Problem Analysis
3. Solution Approach
4. Implementation
5. Input Format
6. Testing
7. Complexity Analysis
8. Discussion
9. Conclusion
1. Objectives
- Represent a network using a weighted, undirected graph.
- Find the shortest path between a source and destination using
  Dijkstra's algorithm.
- Construct a Minimum Spanning Tree using Kruskal's algorithm.
- Construct a Minimum Spanning Tree using Prim's algorithm.
- Use Union-Find to detect and prevent cycles in Kruskal's algorithm.
- Use BFS to trace paths in the generated MSTs.
- Remove a selected edge and analyze the updated paths and network
  connectivity.
2. Problem Analysis
The problem is to design a low-cost network using a weighted, undirected
graph. Each vertex represents a site, and each edge represents a link
with an installation cost.

Dijkstra's algorithm finds the shortest path between the given source
and destination. Kruskal's and Prim's algorithms build Minimum Spanning
Trees to provide alternative network structures. After a selected edge
is removed, the program recalculates the paths and checks whether the
network remains connected. If a path or spanning tree cannot be formed,
the program reports that the graph is disconnected or that no path
exists.
3. Solution Approach
1. Read the number of vertices and edges, followed by the edge details.
2. Store the graph in an adjacency matrix and keep the edge list for
   Kruskal's algorithm.
3. Run Dijkstra's algorithm to find the shortest path from the source
   to the destination.
4. Run Kruskal's algorithm, using Union-Find to construct an MST
   without cycles.
5. Run Prim's algorithm to construct another MST.
6. Use BFS to trace the source-to-destination path in each MST.
7. Remove the selected edge and run the algorithms again to examine the
   updated network.
4. Implementation
Programming language: C

Main algorithms and techniques:
- Dijkstra's shortest-path algorithm
- Kruskal's Minimum Spanning Tree algorithm
- Prim's Minimum Spanning Tree algorithm
- Union-Find (Disjoint Set)
- Breadth-First Search (BFS)
- Adjacency matrix and edge-list graph representations
Save the source code as main.c. The program reads its input from a
file named input.txt.
5. Input Format
The input file must follow this format:
n m
u1 v1 w1
u2 v2 w2
...
um vm wm
s d
ru rv
Where:

  Symbol     Description
  n        Number of vertices
m        Number of edges
u, v     Endpoints of an edge
w        Weight or cost of an edge
s        Source vertex
d        Destination vertex
ru, rv   Endpoints of the edge to remove

Input assumptions: Vertex numbering starts from 0. Edge weights
must be positive because the program uses 0 in the adjacency matrix to
represent the absence of an edge. Dijkstra's algorithm requires
non-negative edge weights.
6. Testing
The supplied project material identifies two test cases but does not
provide their input values or output results. Add the actual test inputs
and captured program outputs here after running the program.

The tests should check:
- The shortest path before edge removal.
- The Kruskal MST path before edge removal.
- The Prim MST path before edge removal.
- The updated shortest path after edge removal.
- The updated Kruskal and Prim MST paths.
- The program's response when removing an edge disconnects the graph.
7. Complexity Analysis
Let N be the number of vertices and M be the number of edges.

  Algorithm / Operation                       Time Complexity in this implementation
  Dijkstra (adjacency matrix)                                                O(N²)
Kruskal (edge sorting and Union-Find)                                 O(M log M)
Prim (adjacency matrix, as implemented)                                    O(N³)
BFS path tracing (adjacency matrix)                                        O(N²)
Edge removal in adjacency matrix                                            O(1)
Space Complexity
- Adjacency matrix: O(N²)
- Edge list: O(M)
- Parent, visited, distance, and queue arrays: O(N)
- MST adjacency matrices: O(N²)
Overall space complexity: O(N² + M).

The algorithms are run both before and after edge removal. For this
implementation, the total time is dominated by Prim's O(N³)
implementation and Kruskal's O(M log M) edge sorting, giving
O(N³ + M log M) overall.
8. Discussion
The program analyzes a weighted, undirected graph using Dijkstra's,
Kruskal's, and Prim's algorithms. Dijkstra's algorithm calculates the
shortest path between the selected source and destination. Kruskal's
algorithm builds a Minimum Spanning Tree by considering edges in
increasing order of weight, while Prim's algorithm grows an MST by
adding the minimum-weight edge connecting a selected vertex to an
unselected vertex.

The program then removes a selected edge and recalculates the paths.
Removing an edge may change the shortest path, the MST structure, or the
connectivity of the network. The results can therefore be used to
observe how graph algorithms respond to changes in a network.
9. Conclusion
This project implements Dijkstra's, Kruskal's, and Prim's algorithms to
analyze a weighted, undirected graph. Dijkstra's algorithm finds a
shortest path between two vertices, while Kruskal's and Prim's
algorithms construct Minimum Spanning Trees. The program also removes a
selected edge and recalculates the paths to examine changes in network
structure and connectivity.

Overall, the project demonstrates practical applications of
shortest-path algorithms, minimum spanning trees, cycle detection, graph
traversal, and network connectivity.
How to Compile and Run
Requirements
- GCC compiler
- A C development environment
- An input.txt file in the program's working directory
Compile
gcc main.c -o graph
Run
./graph
On Windows:
gcc main.c -o graph.exe
graph.exe
The program opens input.txt automatically, so make sure the file is in
the current working directory.
Project: Weighted Graph Network Analysis
Language: C
Algorithms: Dijkstra, Kruskal, Prim, Union-Find, and BFS
Key concepts: Shortest Path, Minimum Spanning Tree, Edge Removal,
and Graph Connectivity
