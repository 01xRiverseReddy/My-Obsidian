
Breadth-First Search (BFS) is a graph traversal algorithm that explores all vertices of a graph in layers, starting from a given source vertex and visiting its neighbors before moving to their neighbors. It works on both directed and undirected graphs and is particularly useful for finding the shortest path in unweighted graphs.


How BFS Works


BFS uses a queue (First In, First Out) to keep track of the vertices that need to be explored. Here’s the step-by-step process:


Algorithm

1. Initialization:

• Start from a given source vertex.

• Mark the source vertex as visited.

• Enqueue the source vertex.

2. Traversal:

• While the queue is not empty:

1. Dequeue a vertex from the queue.

2. Visit all of ’s unvisited neighbors:

• Mark each neighbor as visited.

• Enqueue each neighbor.

3. End Condition:

• The traversal ends when the queue becomes empty, indicating that all reachable vertices have been explored.

  
Pseudocode

  

def bfs(graph, start):

    visited = set()          # To keep track of visited nodes

    queue = []               # Queue for BFS

  

    queue.append(start)      # Enqueue the start vertex

    visited.add(start)       # Mark as visited

  

    while queue:

        vertex = queue.pop(0)  # Dequeue a vertex

        print(vertex)          # Process the vertex

  

        for neighbor in graph[vertex]:  # Iterate through neighbors

            if neighbor not in visited:

                visited.add(neighbor)   # Mark neighbor as visited

                queue.append(neighbor)  # Enqueue the neighbor

  
