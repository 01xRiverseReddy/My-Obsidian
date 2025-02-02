1. Adjacency Matrix

• Description: A 2D array (matrix) where matrix[i][j] represents the edge weight (or 1 for unweighted graphs) between vertices i and j.

• Space Complexity: O(V^2), where V is the number of vertices.

• Advantages:

• Easy to check if an edge exists between two vertices.

• Efficient for dense graphs.

• Disadvantages:

• Requires O(V^2) space even for sparse graphs.

• Iterating through neighbors of a vertex can be inefficient.

  

Example (Undirected Graph):

  

   0 -- 1

    \  |

     \ |

       2

  

Adjacency Matrix:

  `0  1  2`

`0 [0, 1, 1]

`1 [1, 0, 1]

`2 [1, 1, 0]