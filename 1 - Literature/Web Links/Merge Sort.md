
- The idea of merge sort is based of this diagram . 
![[Pasted image 20250417123813.png]]

- We recursively divide the array into two halves , similar to binary search . And when we arrive at points where we can’t divide it further so we start sorting from there . 
- Let’s say we have two halves the idea is that these two halves are two sorted halves at any given moment of time . Where we have to do is just merge them and we get a sorted array . 

The algorithm to merge the sorted array is below 

```
While(i<=mid and j<end){
If(arr[i]<=arr[j]){
I++
}
Else{
Int val=arr[j]
Int ind=j;
While(ind!=i){
arr[ind]=arr[ind-1];
Ind—;
}
Arr[i]=val;
I++;
J++;
Mid++;
}
}
```