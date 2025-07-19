
### Background 

Heap is a binary index tree where certain compliance rules that enables us to query the largest element in a collection in constant time and remove that element and maintain the structure in LogN complexity . 
Operations are - 
1. Push
2. Pop
3. Size
4. IsEmpty


### Use Case 

Heaps’s primary use case is to get the answer to something such as kth largest or shortest element . In such cases we can keep popping from the heap until we get the kth elements . 
Another scenario would be to have the maximum element always at the fingertip for computation . 

Not the most commonly asked data structure in interviews but could be a medium or easy question in the first coding round of selection process . 


Another user case is when we want to simulate a run where we need to stall computation . In this case we can use both Heap and queue conjunctively . 


### Problems 
[[1046. Last Stone Weight]]
[[215 Kth Largest element]]
[[973.Closest points to the origin]]
[[621 .Task Scheduler]]



