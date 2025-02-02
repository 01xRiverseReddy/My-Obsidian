https://leetcode.com/problems/coin-change-ii/description/


### Brute Force 
- The brute force approach would be to generate every possible combination through backtracking . 
- The limiting factor would be to not exceed the amount , when done we can prune the branch . Whenever we reach any result we memorise the result such that the recursive call isn’t duplicated (this is minor optimisation) 
- We maintain a vector of set of vectors to prevent the insertion of duplication . `vector<set<vector<int>>> `
- This would cost `O(n^2)` and this would never work out . 


### Optimal approach 

- The key problem here is the count of duplicates or else this problem could have been achieved in `O(n)` using a singe dimension . Since we have to take duplicates into account we have to go with the two dimensional approach .
- Let’s say  similar to coin change problem but we consider the array of coins as a dimension . 
- We create two loops iterate `i` up till amount and `j` over each coins . At any point in the dp table `dp[i][j]` represents the amount `i` we can achieve using coin up till `j` th index in the coin array . 
- To compute `dp[i][j]` we just need to compute two dimensions . The first being the the number ways we can use the `jth` coin to reach `i` which is nothing but `dp[i-coins[j]][j] +1` and the number of ways we can compute the amount `i` without using the `jth` coin. 
- By computing `dp[i][j]=dp[i-coins[j]][j]+1+dp[i][j-1]` we can reach the desired result for which we are computing . The complexity is pretty obvious `O(n^2)` .