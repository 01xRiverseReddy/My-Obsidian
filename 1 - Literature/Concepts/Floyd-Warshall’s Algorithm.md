
### Background 

Floyd Warshall’s algorithm is to find the shortest path from all nodes to all nodes . In short it is just the same Bellman’s ford but we use edges instead of vertices . This works for negative edges as well and since we are computing for all vertices it takes more time . 


### Intuition 

If we have a graph that is weights directed or undirected we can perform three round of iterations on the vertices to get the shortest distance from all nodes to each nodes . This is kind of like dynamic programming where we don’t exactly or directly compute the result .



### Approach 

- We maintain a regular adjacency list with all the nodes and edges . 
- We maintain a distance matrix where i and j represent the shortest path from i to j .All the values in this distance matrix will be zero except for the vertices where i=j because distance will obviously be zero . 
- We create three loops iterating over vertices .
- In the inner most vertices we check `dp[i][j]=max(dp[i][j],dp[i][k]+dp[k][j]) ` . What this basically means that if for any two point `i and j` we are checking if there exists a middle man node that can interconnects these two nodes . 
![[Pasted image 20250213120712.png]]



Time complexity : `O(v^3) `
