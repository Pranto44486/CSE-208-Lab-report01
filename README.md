Weighted Graph Network Analysis in C
A C programming project that analyzes a weighted, undirected graph using
Dijkstra's, Kruskal's, and Prim's algorithms. It compares
shortest paths and Minimum Spanning Trees (MSTs) before and after
removing a selected edge.
Table of Contents
- Overview
- Objectives
- Problem Analysis
- Algorithms and Techniques
- Implementation
- Input File Format
- How to Compile and Run
- Testing
- Complexity Analysis
- Discussion
- Conclusion
Overview
The project models a network as a weighted, undirected graph: -
Vertices represent locations or sites. - Edges represent
connections between locations. - Weights represent connection or
installation costs.

The program calculates the shortest path between a source and
destination, constructs MSTs using Kruskal's and Prim's algorithms,
removes a selected edge, and runs the algorithms again to observe how
the network changes.
Objectives
1. Find the least-cost path between a source and destination using
   Dijkstra's algorithm.
2. Construct a Minimum Spanning Tree using Kruskal's algorithm.
3. Construct a Minimum Spanning Tree using Prim's algorithm.
4. Use the Union-Find technique to prevent cycles in Kruskal's
   algorithm.
5. Use Breadth-First Search (BFS) to trace the path in an MST.
6. Remove a selected edge and analyze the updated network.
7. Check whether a valid path or connected MST remains after edge
   removal.
Problem Analysis
The problem is to design and analyze a low-cost network using a
weighted, undirected graph. Each vertex represents a site, while each
edge represents a link with an associated installation cost.

Dijkstra's algorithm finds the shortest path between the selected source
and destination. Kruskal's and Prim's algorithms construct Minimum
Spanning Trees to represent low-cost network connections. The program
then removes a selected edge and recalculates the paths and MST-based
routes. If the graph becomes disconnected, a valid connection may no
longer be possible.
Algorithms and Techniques
  Algorithm / Technique               Purpose
  Dijkstra's Algorithm                Finds the shortest path between the
source and destination.

  Kruskal's Algorithm                 Builds an MST by selecting edges in
increasing order of weight.

  Prim's Algorithm                    Builds an MST by repeatedly
selecting the minimum-weight edge
connecting selected and unselected
vertices.

  Union-Find (Disjoint Set)           Detects cycles while constructing
the MST with Kruskal's algorithm.

  Breadth-First Search (BFS)          Finds and prints the
source-to-destination path in the
constructed MST.

  Edge Removal                        Removes the selected connection and
allows the algorithms to analyze
the updated graph.
Connectivity Checking               Detects when a spanning tree or
route cannot be formed.
Implementation
The program is implemented in C and uses an adjacency matrix to
represent the graph. It also stores the edges in an edge list for
Kruskal's algorithm.

Main implementation components: - dijkstra() calculates and prints the
shortest path. - kruskal() constructs an MST using sorted edges and
Union-Find. - prim() constructs an MST by selecting minimum-weight
connecting edges. - find() and join() implement the Union-Find
operations. - printPath() uses BFS to trace a route through an MST. -
main() reads the input file, runs the algorithms, removes the selected
edge, and runs the analysis again.

Save the C source code as main.c and place the required input.txt
file in the program's working directory.
Input File Format
The program reads input from a file named input.txt.
n m
u1 v1 w1
u2 v2 w2
...
um vm wm
s d
ru rv
Input description: - n = number of vertices - m = number of
edges - u, v = endpoints of an edge - w = weight of an edge - s
= source vertex - d = destination vertex - ru, rv = endpoints of
the edge to be removed

Important notes: - Vertices are represented using integer indices,
normally from 0 to n-1. - The adjacency matrix uses 0 to represent
the absence of an edge; therefore, edge weights should be positive. -
Dijkstra's algorithm requires non-negative edge weights.
How to Compile and Run
Linux / macOS
gcc main.c -o graph
./graph
Windows (MinGW)
gcc main.c -o graph.exe
graph.exe
Make sure input.txt is available in the program's current working
directory before running the program.
Testing
The supplied project document contains headings for Case01 and
Case02, but does not include the actual test inputs or outputs. Add
your verified test cases here before publishing.

For each test case, include: 1. The contents of input.txt. 2. The
program output before edge removal. 3. The program output after edge
removal. 4. Whether the graph remains connected.
Complexity Analysis
Let: - N = number of vertices - M = number of edges

  Algorithm / Operation                           Time Complexity in This Implementation
  Dijkstra (adjacency matrix)                                                    O(N²)
Kruskal (edge sorting + Union-Find)                                       O(M log M)
Prim (nested scans of the adjacency matrix)                                    O(N³)
BFS path tracing (adjacency matrix)                                            O(N²)
Removing an edge from the matrix                                                O(1)
Space complexity                                                           O(N² + M)

Overall note: The implemented Prim's algorithm scans the adjacency
matrix to find the next minimum edge in each of up to N-1 iterations.
Therefore, its time complexity is O(N³) in this implementation. The
overall time for a complete run before and after edge removal is
dominated by O(N³ + M log M).
Discussion
The program analyzes a weighted, undirected network using three graph
algorithms. Dijkstra's algorithm calculates the shortest path between
the selected source and destination, while Kruskal's and Prim's
algorithms construct Minimum Spanning Trees. After a selected edge is
removed, the program recalculates the routes and MST results. Comparing
the results helps show how removing a connection can affect network
paths, total connection cost, and connectivity.
Conclusion
This project demonstrates the use of Dijkstra's, Kruskal's, and Prim's
algorithms in weighted graph analysis. It finds shortest paths,
constructs Minimum Spanning Trees, and examines the effect of removing a
selected edge. The program helps compare different graph algorithms and
understand the importance of maintaining connectivity in a low-cost
network.
Language: C
Project Topic: Weighted Undirected Graph Analysis
