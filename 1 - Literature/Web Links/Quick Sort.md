
- The algorithm of quicksort is similar to merge sort where we recursively divide the array into two halves but the way we sort the halves is different . 
- Given an array of nums , at each recursive iteration we first take a random number in the array, or not, Probably the last element of the array and we find the position of that number in the sorted array .
- While doing this what we do is make sure that all the elements to right of this position are greater than this number and to the left are the numbers lesser than it . 
- We will eventually repeat this process for the two parts of the array, the right hand side and the left hand side of this pivot . 
- Now the question is how do we have do it the pivot finding and partial sorting . This is pretty simple , I have run it inside my head and I can achieve this live in an interview as well . 


