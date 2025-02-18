
### Background 

Bellman-Ford’s algorithm is also used to find shortest path between single node to all the nodes . What distinguishes this algorithm from Dijkstra’s is that it works guaranteed when dealing with negative edges  . The only problem is that the algorithm is slower compared to Dijkstra’s . 



### Intuition 

If there are E edges in a graph , between any two vertices , there can be almost E-1 edges . We can perform E^2 iterations on the entire graph and populate the distance array based on availability and we would have covered all possibilities . 


### Approach 

- Take all the edges and store them in an array , an edge list basically . 
- Maintain a distance array with all values set to infinity other than the starting index , which should be marked as zero . 
- ![[Pasted image 20250213105804.png]]
- We iterate over the edge list and whenever we find a path , for instance there is an edge from S->A , we populate the minimum of those values . ![[Pasted image 20250213110054.png]]
- If we come across a new node like B which does note have a direct edge , we will check the dependent edge like C and take the cost to get to C plus the edge C->B .
- We repeat this process E time and then we would have the distance array successfully populated . 




Time Complexity : `O(E*E) ` 
