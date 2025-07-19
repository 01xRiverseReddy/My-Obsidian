
### Background 
Prim’s algorithm to find minimum cost spanning tree is a simple algorithm . When given an undirected weighted graph , we have to find a tree such that the sum of the entire weights of the tree is minimum . 


### Algorithm 

- We take any random edge and examine its edges . From all the possible edges , we take the minimum edge and consider it as a part of our tree . 
- From the edge which we start , we first consider it as visited and add all its edges to the priority queue . 
- From the priority queue we keep popping until we find an edge that has not been visited . 
- We keep repeating this process until our tree is full . 

![[Pasted image 20250304104910.png]]




### Literature 
[[Prim’s Algorithm to find minimum cost spanning tree]]