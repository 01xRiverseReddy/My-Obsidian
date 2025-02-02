• Description: An array (or list) of lists. Each vertex has a list of its neighbors (or edges).

• Space Complexity: O(V + E), where E is the number of edges.

• Advantages:

• Efficient for sparse graphs.

• Space-efficient compared to adjacency matrices.

• Disadvantages:

• Checking if a specific edge exists can be slower.

• Implementation: Typically uses hashmaps or arrays of lists.

  

Example (Directed Graph):

  

   `0 -> 1 -> 2

  

Adjacency List:

`0: [1]

`1: [2]

`2: []


Adjacency Set

• Description: Similar to an adjacency list, but uses sets instead of lists for neighbors.

• Space Complexity: O(V + E).

• Advantages:

• Faster edge existence checks.

• Useful for graphs with unique edges.

• Disadvantages:

• Requires extra overhead for maintaining sets.