https://leetcode.com/problems/coin-change/description/




### Brute Force 

- Since we have an array of coins , we can generate combinations of them and check to see if the size we have received is the minimum . 
- This approach is flawed for the main reason being is that the combinations generated will far exceed the number of operations we are confined to . 
- Hence we have to selectively prune the combinations .


### Optimal Approach 

- Since we have an array of coins and an amount we have to achieve with the most minimum approach . We can create a dynamic array to track the minimum number of denominations for each possible amount . 
- For instance if we have coins `[1,2,3]` and amount `6` . The minimum coins we can use to achieve 6 would be the minimum of the minimum coins used to achieve 5(6-1) , 4(6-2) , 3(6-3) . 
- We are basically checking checking the sub-problem and seeing if we can get to the desired amount for any one less denomination .  
 - We initialise and array as `dp` and only the first index would be populated as 0 while the rest as -1 . Since 0 is always achievable without using any denomination at all . 
 - We the iterate over the amount array and if an index is not -1 ( which means that it is not possible to get to that amount ) , iterate over the coins from inside . If we get i+j as less than the amount then we populate it as `dp[i+coins[j]]=min(dp[i]+1, dp[i+j])` .  

![[Pasted image 20250124150604.png]]
- In the End we return `dp[amount]` 