
### Background 

DFS is a traversal algorithm which means that it is used to explore . It is not specifically limited to graphs , it can be used a form of searching as well . The idea behind DFS is to go all the way to the last reachable point before exploring the initial possible paths . 


### Approach 

- At any given point we take the node , or any form of data point and then we take the first form of connection . 
- After we move to the child of the node/data point , we then move to the child of this node/data point . 
- We repeat this process until we find a node/data point that has no children or it has already been visited . 
- After we have found such a data point we move back to the previous node and repeat this entire process on the next child . 


### Algorithm 
We can implement this in both iteratively using stack or recursively . Here I am choosing the recursive path .
- We start a data point , we check it’s already been visited . If it has then we stop and we do not do anything . 
- If not , we consider this node as visited and then we check for the children . 
- As soon as we get the first child we recursively run DFS .
- This process keeps getting repeated until we have visited all the nodes/data points . 

