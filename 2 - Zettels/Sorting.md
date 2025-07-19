
### Intro 

Sorting problems in problem solving are not directly straightforward , I somewhat struggle to solve them . All sorting questions will usually be constrained within 1e5 input size and sometimes between 1e4 where they expect you to perform some operation in polynomial time . 




### Sorting Algorithms 

Sorting algorithms are endless in my opinion . There is always some or the other complex sorting algorithm out there doing some complex operation . The main algorithms that could probably get asked in the interview are these below . 

- Selection sort : This sort take place in O(n^2) and variations of this can be asked in questions 
- Bubble Sort : This is also O(n^2) but best case O(n) if the array is sorted . 
- Insertion Sort : This is also O(n^2) but on an average it performs a little better than both bubble and selection sort . 
- Merge Sort : This is a very important sort . Variations of this sorting algorithm are all over the hard problem section on leetcode . This happens in O(nlog(n)) and the algorithm is explained in the literature notes . 
- Quick Sort : This algorithm is the fastest and is in O(nlog(n)) . A modified version of this is used in the standard sorting STLs . 

There is a mathematical proof that sorting of any array with n elements cannot be done in faster than O(nlog(n)). 


### Problem Types 

- If a question is being asked on top of sorting , it is usually or if not almost all of the time based on sorting with a custom comparator . After being sorted with the custom comparator , the problem usually demands some logical processing to arrive at the solution . 
- Sometimes they ask fuck all sorts or techniques radix sort or bucket sort or whatever the fuck . In those cases if you do not know , you can just chuck it . 






Literature : [[Bubble Sort]]  [[Insertion Sort]]  [[Selection Sort]]  [[Merge Sort]] [[Quick Sort]]
