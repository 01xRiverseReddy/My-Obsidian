
### Background 

B-Trees are used in Database management systems to effectively store and retrieve data . They are structured in a specific way to reduce the computation required to retrieve data . 


### Disk Structure 

Data is in a hard disks on rough outline , is stored in the form of blocks . The disk is divided into tracks and the tracks are further divided into sectors  . Each Sector holds a certain number of blocks and these blocks are where the raw data is stored . 
The data can be classified as records and each record has an address which is called **Offset**.
![[Pasted image 20250303115522.png]]


### Naive Data Reads 
For the program to read the data that is stored on the disk , it is first retrieved to the RAM and then it is read . Which means that If we have 100 blocks , the 100 blocks are first copied to the RAM and then each block is checked and then we finally have the records we would want to read . 


### Indexing 
Regardless of how many records we need to read from a block there is no option but to retrieve the entire block and read . How indexing works is that we have a seperate block dedicated to storing the block where the data is present . For instance we will know the at records numbered from 1-10 will be stored in Block A so if we need to read record 1 we maintain a map with key as 1 and value as A . 
**Multi-Level Indexing** - This is where we implement indexes for indexes because as the database grows , having one index is not sufficient . 
![[Pasted image 20250303121634.png]]


### M-Way Search Tree

- M-Way Search Tree is an extended data structure of binary search trees . In binary search trees , for each node we have M children . 
- Similar to binary search trees these trees maintain a structure to perform queries in a more optimised manner . 
- Each node has M-1 keys which are in sorted order . Each key points to a child node such that the child nodes has a value that is greater than the before key but less than the current key . 
- M-way search Tree looks fine on the outside but in its real life implementation , M-Way search tree can become skewed . 


### B-Trees and B+ Trees

B-Tress and B+ Trees are a safe ways make sure that the m-way search trees are not skewed . 
There are a certain rules that enforced so that the structure of m-way search trees . 
1. `[m/2]`  children  are minimum 
2. Root can have a minimum 2 children 
3. All leaf nodes at same level 
4. The tree is built bottom-up . 

The building of B-Trees can be seen through the video lecture of Abdul Bari . It is sort of shit but the bottom line is that they are built for multi level indexing and making optimal read and writes . 









### Literature 
[[B and B+ Tress - Abdul Bari]]