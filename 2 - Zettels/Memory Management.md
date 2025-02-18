
### Structure 

- The memory of a program is divided into four segments , the code , global/static , stack , heap . Each of these segments have their own unique use case . ![[Pasted image 20250205120757.png]]




### Code Segment 

- The code/text segment of the program’s memory stores the compiled machine code . 
- This is read-only segment to avoid accidental over-writes . 
- This segment gives us a more clear view on how function pointers work . Function are nothing but a series of instructions present on the memory . If we know the starting addresses of these functions on the code segment then we can invoke them at out comfort . 


#### Data Segment  and BSS Segment 
- Data segment is the area where both global and static variables are stored . 
- The data segment is initialised into two segments , the initialised block and the uninitialised block . 
- Initialised block is the block that has the global and static variables that have been explicitly declared whereas the uninitialised block is the block that has variables that are yet to be assigned values . 



### Stack 

- This also known as the function memory , and this is the segment where all the instructions are executed .
- As the name suggests  this uses the stack data structure . 
- And the reason it gets its name function memory is because whenever a function gets executed it gets a new execution space allocated in the stack memory called Stackframe . Each function has a limited set of memory called stackframe and is cleared as soon as the function execution is complete . 
- A key thing to remember is that if a pointer is created in one function and reused in another function through return variables . It is most likely to not work as expected for the reason being is that the memory would be cleared out hence the dereferenced value would be something random . 


### Dynamic Memory / Heap 

- Dynamic memory is when we want to allocate memory during runtime . The reason dynamic memory exists is because during compile time the memory allocated to each stackframe is fixed hence we cannot go beyond . 
- Using dynamic memory we can always allocate and de-allocate memory . 
- For instance we have a user that requested an array of size 10^6 . During runtime we can specially allocate memory . 
- There are special functions to allocate and de-allocate memory , which are Malloc , Calloc , realloc and free. 
- Free is an important function as it takes an address and frees it . Without freeing the memory in the Heap we would always be allocating memory and leave it occupied which would leave no room for future instructions to execute . 




Literature : [[Pointer and Memory Management]]