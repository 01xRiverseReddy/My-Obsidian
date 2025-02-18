https://youtu.be/zuegQmMdy8M?si=uSiVQaqZTmGT2DFN

### Context 
- In few programming languages when a program is executed , a variable as soon as it is initialised gets added to the lookup table such that the address of the variable can be accessed by taking the name of the variable as key .
- There exists a special type of variable that stores the address of an other variable , thereby enabling to access the value held by it (dereferencing ).
- A pointer is initialised using `int* p` and asterisk indicates that the variable is a pointer and to get the address of any variable we use the ampersand operator `int a=5 ; p=&a’` .
- The above expression gets the address of the variable ‘a’ and assigns it to ‘p’ . Which means that p holds the value for the address of ‘a’ . And to dereference the value held at ‘a’ , we use `cout<<*p<<endl;` 


### Use Case 

- The key use case of pointers is that when we can mutate the variable held in the pointer and have it reflect it in the original variable . For instance `*p=8; cout<<a<<endl;` this will cause the variable in to be mutated . 
- The key thing to remember is if we forget the asterisk , we are cooked because we would be overwriting the memory . 
- This is mainly used in implementing linked lists , trees etc. 
- I like to call this as pointer chaining when one pointer stores the location of another pointer . The thing with pointer chaining is that you can do it for a really long set of links and whenever you mutate the dereferenced value it updates on the actual variable . `int** p` is how a two chained pointer would look . 


#### Program Memory Structure 

- Whenever a program is run a certain amount of memory is allocated to the program from the RAM . 
- There’s four type of memory allocated 
- **Code** is the area of the memory that simply stores the code that is being executed . 
- **Global/Static Variables** is the special area allocated for Global and Static variables for easy access . 
- **Stack** is the most famous form of memory know to a programmers . This is where the local variables of the function being called are stored . Whenever a function gets called a certain memory gets allocated on the stack and this is known as stackframe and this is basically the scope of this functions memory . When the Function Calls another function within it a fresh stackframe is allocated to the newly formed function . To this newly formed function the parameters that are passed while calling are called actual parameters . These parameters are then locally copied to the stackframe and these are known are formal parameters . But when a pointer is initialised in the function parameters , this copying is skipped and therefore a lot memory would be saved on a bigger scope . 

### Array and pointers 

- Pointers work somewhat the way we would expect in c++ when it comes to arrays . 
- When an array is initialised we can store the pointer of an index regularly as we would expect like `int* p=&a[i]` . 
- We can also do something like `int* p=a` and in this case if a is an array . This would assign the zeroth index address to the pointer variable . 
- Passing arrays as function variables work entirely differently . When ever we pass an array as an argument in function , it does not create a full copy of the array as it is both expensive in time and space . Instead what it does is , it just creates a pointer to the zeroth index of the array . Basically `fun(int a[])` is the same as `fun(int* a)` 



### Intense fucking around with Arrays and Pointers 

- Arrays and pointers work pretty simply when it is one - dimensional arrays we are dealing with . But as soon as dimensions get added the complexity increases but the fortunate part is that it’s not rocket science yet . 
- We are ware the if an array `int a[]`  exists , the value of `a==&a[0]` . And the fact that we can easily assign it to a pointer `int* p=a or int* p=&a[0]` . But as soon as `int a[][]` we cannot do `int* p =a` because ‘a’ will return a pointer to pointer which is again `&a[0]` . So incrementing ‘a’ by 1st would push the array a by entire dimension . So a+1 would basically give us `&a[1]` .
- **How do we assign pointer to multidimensional arrays** - When need to hold a pointer that confines the sub-array of only one dimension . Which means that the pointer we want can store the dimensions starting pointer . For instance if we have `int a[2][3]` then we can have a pointer `int* p[3]=a ` , this expression gives the starting pointer of `a[0]` .
- **Passing to functions** - To pass a multi-dimensional array to functions we can do the regular passing where `func(int a[])` which will just give the address of the first dimension . What we can also do is (what I am thinking ) is `func(int a[], int sizeOfArray)` so that we can completely iterate over the array . The alternate working solution is if it’s a two dimensional array we can do `func(int* a[3])` or `func(int a[][3])` which is at the end of the day , the same thing . Only the first parenthesis’s of the multi-dimension array can be blank while the rest have to be populated . For example for a three dimensional array `int c[1][2][3]` we have to populate `func(int c[][2][3])` or `func(int* c[2][3])` . Any mismatch in the dimensions while passing the array can result in a compilation .


### Dynamic memory allocation / Using Heap 

- To allocate memory dynamically to stack we need to use the heap memory because the memory for stack is static and fixed . 
- There are 4 memory functions used to allocate memory and deallocate . 
	- Malloc - Malloc take one parameter and it is the size that is to be allocated in bytes and then it goes to create space in the heap . The pointer returned by Malloc is a void pointer hence it has to be typecasted . 
	- Calloc - Calloc’s speciality is that it takes two parameters the number , size of the ‘number’ that is to be initialised. Calloc too return a void pointer and has to be typecasted to dereference . Calloc initialises all the memory that has been allocated to 0 . 
	-  Free - What Free does is it take blanks out the memory blocks , It just takes the pointer as parameter and blanks it out . 
	- realloc - Realloc essentially takes an existing allocated memory on the heap copies it and returns the base pointer so that it can be used later on . It takes two parameters the base pointer and the amount of memory to be allocated . 



### Pointer as function returns 

- pointer as function returns are exactly what they sound like . We return an address location instead of an explicit variable . 
- There are some dangers to how we managed the returned address . If we go ahead and create a pointer in the conventional way and return it , the pointer memory will get de-allocated as soon as  a new function is called since it will be stored on the stackframe .
- So the pointer that is to be returned must be created on the heap . 


### Function Pointers 

- Function pointers are basically the address function but how does it work ? 
- Whenever a file is compiles , it gets converted to machine code and this machine code is stored on the code segment of the memory layers . Any function in machine code is a set of instructions that have been recorded on the memory and if we know the starting address of these functions we can figure out how to fire the function at our will or even better have the code do that . 
- The main use case of this callback functions . 


### Memory Leakage 

- Memory leakage is a phenomenon that happens when we keep allocating memory on the heap but never proceed to clear it . 
- This is a hazardous phenomenon as the memory on heap will eventually run out and the memory that could have been used for other task would have been occupied for nothing . 
- This leads to performance degradation .
