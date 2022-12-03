
#### Pseudocode of Dijkstra's using Priority Queue:

~~~
1  function Dijkstra(Graph, source):
2      dist[source] ← 0                                    // Initialization
3
4      create vertex set Q
5
6      for each vertex v in Graph:           
7          if v ≠ source
8              dist[v] ← INFINITY                          // Unknown distance from source to v
9              prev[v] ← UNDEFINED                         // Predecessor of v
10
11         Q.add_with_priority(v, dist[v])
12
13
14     while Q is not empty:                              // The main loop
15         u ← Q.extract_min()                            // Remove and return best vertex
16         for each neighbor v of u:                      // only v that is still in Q
17             alt ← dist[u] + length(u, v) 
18             if alt < dist[v]
19                 dist[v] ← alt
20                 prev[v] ← u
21                 Q.decrease_priority(v, alt)
22
23     return dist, prev
~~~


# Program Description:
Programming Language : JAVA
Compiler Version: JDK 1.8.0_151
OS: Linux Workstation

# Compile the program:
Before building the java class file make sure java(i.e jdk1.8) is installed in the system.

##### Command to build java class files:
___
~~~~
javac Graph.java
~~~~

Once the above command is executed, a class file named filename.class is created

# Run the Program:
Arguments passed are
~~~
InputfileName - The file which has the nodes of the network with weights
~~~

##### Command to run java program:
___
~~~
java ClassName InputfileName < QueryfileName > OutputfileName
Example: java Graph network.txt <  queries.txt > output.txt
~~~
Note: ClassName has the main function

# Data Structure:
1. **Heap data structure** is used to implement the algorithm and have design min binary heap (priority queue) where smallest element has the highest priority (root node in tree shape)
2. **HashMap data structure** is used to store information about the vertex 
3. **LinkedList** data structure is used to add all the edges of the graph
4. **TreeSet** data structure stores the visited nodes  [Sorted sort, no duplicate values]. It sorts the vertex in alphabetical order useful while printing the graph.

# Implementation:

Implementation code is in single file Graph.java which has complete 5 tasks required for the project. The algorithm implemented is an algorithm used to find the shortest path between nodes in graph called as Dijkstra's Algorithm. Adding to the above task, the reachable vertices task is accomplish using recursive algorithm (not using the shortest path algorithm described above) to find the vertices connected to each vertex. The task of reachable is achieved in O(n logn) time, where n = Number of vertices.

Classes used to achieve the implementation are:

1. **Graph:** Build the network Graph using input file and perform operations based on query file on the network. 
2. **Vertex:** Vertex class is used to represent vertex of the graph.
3. **Edge:** Edge class is used to represent edges of the graph.
4. **Path:** Path class stores name and distance of path.
5. **Pair:** Pair class represents the String pairs.
6. **Heap:** Heap Class is use to efficiently design Dijkstra's Algorithm using concept of minimum priority queue.
7. **GraphException:** Used to signal violations of preconditions for shortest path algorithms.

# Task:
1. **Building the Graph:** Using network input file we will build our graph. We have use double to handle the floating point distance. Each input link is represented by adding two edges, one in each direction
2. **Changes to the Graph:** All the operations for the changes of the Graph are present in the Graph class.
3. **Finding the Shortest Path:** Using Dijkstra's algorithm we will compute the shortest path distance, and we have implemented using Heap Data structure (Min priority queue).
4. **Print Graph:** We have used TreeSet datastructure to obtain the vertex in alphabetical order, and no duplicates.
5. **Reachable Vertices:** For every vertex, we have find the reachable vertices inn alphabetical order and we have not use the shortest path algorithm to compute that.
### The algorithm used is describe as below
___
~~~~
    ALGORITHM checkReachable( )
  	1. Sorting all the vertices in alphabetical order
  	2. FOR each vertex which is "up" in the list
  	3. 		PRINT vertex_Name
  	4.		BUMP vertex to visited_node list
  	5.		CALL reachable(vertex)
  	6.	END FOR
  	7.	PRINT all the Vertices from visited_nodes in alphabetical order

  	ALGORITHM reachable(vertex)
  	1. FOR each adjacent vertices
  	2.		IF edge is down OR vertex is down THEN
  	3.			CONTINUE;
  	4.		END IF
  	5.		IF Vertex exists in visited_node list THEN
  	6.			CONTINUE
  	7.		ELSE
  	8.			BUMP vertex to visited node list
  	9.			CALL reachable(vertex)
  	10.		END IF
  	11.	END FOR
~~~~

## **Complexity:**
The algorithm checkReachable() will be called for every n vertices. So it will take O(n) running time. The recursive call to reachable() will call recursively for every adjacent vertices. So it will take O(logn) running time. Therefore, the overall running time of the algorithm will be O(n logn).

# SingleSourceShortestPathProblemDijkstrasAlgorithim
