
### Background 

Dijkstra’s algorithm is an algorithm to find the shortest path between two nodes . This algorithm is works on the directed and undirected weighted graphs . This is quite often used in networks , maps etc . This is a pretty common algorithm that surfaces in interviews . This uses the heap data structure and this algorithm may or may not work if the nodes have negative edges . 


### Approach 

Dijkstra’s algorithm aims to solve the shortest path problem literally by traversing each edge of a vertical . It start’s from a vertex and assumes that each and every other vertex’s distance from it is infinity . As we traverse from edges and find a vertex we conclude that the distance to that vertex is the minimum of current distance and what the distance that has already made it there . We repeat this process until we have an actual minimum to the edge node . 



### Algorithm 

- Initialise a distance array with each index corresponding to a node of the graph such that it represent the distance from the starting node to every other node . Initially all the numbers in the indices would be int_max except for the starting node which would be zero because the distance from the node to itself is obviously zero .
- We then initialise a priority queue of `priority_queue<pair<int,int>> ` and add the starting index as `make_pair(0,start) ` . 
- We pop the priority queue and check the node and see all its edges . If we can reach a vertex in a distance that is less than what is already there in our distance array then we update the distance array and we add the new pair `make_pair(pq.top().first+adl[pq.top().first].second, j) ` .
- We repeat this process until we have our priority queue empty . This way we will eventually get the shortest distance from start node to all the nodes . 



Time Complexity - O((V+E)LogV) 


