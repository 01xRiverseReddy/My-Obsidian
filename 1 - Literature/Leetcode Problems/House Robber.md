
https://leetcode.com/problems/house-robber/description/

### Brute force 
- The brute force approach is to generate every possible combination of the house array and Pick the houses that are not adjacent to each other . 
- This would work if the array size is less than 12 because the complexity of this method is `O(2^n)` .

### Optimal Approach 

- The optimal approach is that we have only one branch of sub-problems and we have to choose between the two of them . 
- If we are at a house `i` we cannot choose `dp[i-1]` result and add it to `arr[i]` to get the result of `dp[i]` because they are adjacent . 
- We have to choose either `i-2 or i-3` since they are not adjacent so `dp[i]=max(dp[i-2],dp[i-3])`