
### Intro

- Pointers are variables that store memory addresses of other variables . They are present in low-level languages like c and c++ . In many other languages , they are absent like Java where it’s prime principle is memory safety . In Java references are used instead of pointers.
- Pointers have data types which mean that they are type strict and only pointers of a specific data type can hold the address of variables of a specific type . 
- Pointers can also be used a pivot to access other memory locations from the address that it hold . This is how arrays work . 


### Pointer Syntax 

- A Pointer is initialised using the syntax `<data-type> * <var-name>` . The asterisk is the differentiating factor when it comes to pointer variables . 
- To access the address held by the pointer , we just use the variable name `<var-name>` . 
- To access the **value** held by the address , we use the variable name with asterisk `*<var-name>` ![[Pasted image 20250205102934.png]]

- In the above example we are initialising a pointer and we are getting the address of a variable using the ampersand . To get the address of a pointer , we don’t need to use the ampersand we can just use the variable . 
- To assign the value to the address held by a pointer we assign by dereferencing it first using the asterisk . 



#### Mutating Pointer values
- Whenever the value held by a pointer is mutated at any point , the value of the variable changes with it .
- This operation happens the other way round as well . If the value at variable is changed then the value the dereferenced from the pointer will be mutated as well . 



### Arrays 

- Arrays and pointers work differently . When we declare a pointer to an array we don’t essentially have a pointer to the entire array’s elements . We instead have a pointer to the first element of the array . 
- To Get the address of the first element of the array we just have to use the variable name . Ex if the array is `int arr[3]`  we get the address of the first element by using `arr`  which is the same as `&arr[0]` . 
- We assign the address of the array to the pointer by either `int* ptr = arr` or `int* ptr=&arr[0]` . 
- We can also index the array and get the address of a specific index like `arr+3` which is the same as `&arr[3]` . Simultaneously we can also dereference them by `*(arr+3)` which is exactly the same `arr[3]` . 
- Passing array as parameters to functions - When we declare a function as parameter we do it by `func(int arr[])` which is in reality the same or if not actually `func(int* arr)` . What it does is it points to the actual address of the first variable so that we can later dereference by our method of choice `*(arr+3) or arr[3]` .


### Multi - Dimensional Arrays 

- Multi-dimensional arrays work a little different when working alongside pointers . When we have a multi-dimensional array like `int arr[2][3]` we might naturally assume that assigning it like the previous way would work just fine `int* p=arr` . Wrong , it does not . 
- The thing is that pointer can only hold the starting address of a specific data-type since it is type-strict . If we were to actually change types then we could do something like . `int (*p)[3]= arr` in the previous expression we are declaring that the pointer p is the start address to a 3 dimensional array within arr .
- Whatever it is the data-type must be consistent with that to pointer type . For instance this is valid `int c=[2][3][4]` and a pointer `int (*ptr)[3][4]=c[0]`



### Functions as pointers 

- We can declare a function pointer with the syntax `<return-type> *<variable-name>(function arguments comma separated);` 
- We can declare it for example like this `int *ptr(int,int)` . 
- We can assign the address of the function in the regular conventional way like `&add` . And then we call function in the pointer in the regular way `p(2,4)` .
- Callaback functions work in the exact same manner , the specify a function pointer as argument and then call . 





Literature : [[Pointer and Memory Management]]