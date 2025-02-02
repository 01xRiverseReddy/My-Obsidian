
### Background 

BFS is a traversal algorithm which means that it is used to explore . It is not specifically limited to graphs , it can be used a form of searching as well . The idea behind BFS is to explore the children of the node/data point before moving on to the next layers . 


### Approach 

- At any given point we take the node , or any form of data point and then we take the first form of connection . 
- After we move to the children of the node/data point , we first explore all the children .
- After exploring the children , we repeat this process on the children of the children . 
- At some point we will have visited all the nodes/data point  . 


### Algorithm 
We can implement this in both iteratively using queue or recursively . Here I am choosing the iterative approach . 
- Take a data point , check if it is visited . If visited then we ignore else , pop that from the queue and then add all the children of that data point to the queue .
- After popping we mark the data point as visited so that we are not stuck in an endless loop . 
- We then repeat this process until we have traversed all data points . 



