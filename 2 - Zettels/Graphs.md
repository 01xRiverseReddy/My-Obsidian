
### Intro 
- Graph is a data structure where two data point have some form connection and are linked together to from an Edge . 
- Vertices are the data points when connected that form an edge . 
- An Edge on the Graph can have a direction or it can be bi-directional . Directions are used to establish a more meaningful relationship between two vertices . 
- Each edge in a graph can have a weight associated with it just to add some form of information/ cost to signify a relationship between two vertices. 




### Representation 
Graph representation is basically the ways in which a graph can be stored in a program so that we can work on it . There are only 3 main forms of representation -

1. [[Adjacency Matrix]]
2. [[Adjacency List]]
3. [[Edge List]]


###  Traversal Algorithms 

Graphs have various algorithms in place for different purposes . 

- **Traversal algorithms** are used to travel through the graph , visit every vertex of the graph 
	- [[Depth-First Search]]
	- [[Breadth-First Search]]
	- Topological Sort- it is the exact same as DFS but we store the order of search in the form of last to first . 


### Shortest Path Algorithms 

These algorithms are used to calculate the shortest path between two nodes in a weighted graph , directed or undirected . None of these algorithms work on graphs with negative cycles since there is no solution to that . 
These algorithms mainly involve using a distance array to calculate the distance from the start node to other nodes and continuously update through iteration . 

- [[Dijkstra’s Algorithm]]
- [[Bellman-Ford’s algorithm]]
- [[Floyd-Warshall’s Algorithm]]


### Minimum Cost Spanning Tree

These algorithm help you find the minimum cost to derive a tree from an undirected weighted graphs . 

[[Prim’s Algorithm for minimum Cost Spanning Tree]]
