https://youtu.be/aZjYr87r1b8?si=3lgAkcEIAoOeSW8u



- In this video Abdul Bari explains how from disk structures , index tables to the structuring of B trees and B plus trees 
- He starts off by the structure of the disk . How each disk has Sectors (multiple) and multiple sectors have blocks . These blocks collectively store the rows in a table . Each block has a size allocated to it which means that only a fixed number of records are allocated . The address of each record on the block is termed as **Offset** . 
- If we have have N block then to retrieve any number of records we have to go through n blocks . The reason this is a problem because to read data We need to copy them to RAM and go through each block which means we would have to copy N blocks to RAM and then Read them which is expensive . 
- With Having index’s of any column mapped to offset , the cost of storage is much less and we can fit all of them to the entire much lesser blocks and find the records we need . 
- Multi-level indexing is creating multiple levels of indexing to minimise the calls to read multiple blocks . 
- To have multi-level indexing implemented , we have m-way search trees . M - way search trees are exactly like binary search trees but binary tress are for two nodes , in M - Way search trees we can have M nodes . The problem with M-way search trees is that they are not confined by any set of rules. B-Trees are M-way search trees with rules . 
- 