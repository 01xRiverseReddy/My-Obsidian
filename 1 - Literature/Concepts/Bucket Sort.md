Bucket Sort is a non comparison based algorithm , an algorithm which does not involve comparing any two elements . It is similar to counting sort .

But there is a catch to bucket sort .  It does not involve comparison only if the elements are singular in distribution . Explained in much detail further . 


Algorithm :
1. The bucket sort algorithm involves having an array (extra space) with the same length as the original array , where each index is called a bucket . 
2. All the number of the array should be converted to floating numbers , i.e , 1842 = 0.1842  or 824=0.824
3. After each number is converted to their respective float , iterate over the array and store each number in the index that corresponds to first floating digit by getting the INT of the product of (arr[i] * n ) where n is t
4. After each of them being in their respective buckets , Iterate of the bucket array and just write the original array in the order . 
5. ==the buckets have multiple numbers in them , then they would have to sorted via insertion sort and then be proceeded to step no. 4 .== 

Time Complexity :
Worst Case - O(n^2) , when one bucket has all the numbers and insertion sort has to be performed on all elements . This can be reduced to O(n log n ) by using a faster sorting algorithm . 

Average Case - O (n+k) , when k is the average size of the bucket .


Space Complexity : O(n+k)

Video : https://www.youtube.com/watch?v=VuXbEb5ywrU
link :https://www.geeksforgeeks.org/bucket-sort-2/