

### Brute Force
- brute force approach would be to take the smaller text , create all possible subsequences which would take `O(2^n)` and then iterate over each of the substring to find the longest common subsequence which is `O(m)`. 
- The combined complexity would be `O(m2^n)` and this my grandchildren would live to see the result if both the strings exceeded 100. 

### Optimal Approach 

- Similar to coin change II problem , we would have to go multidimensional to compute the results . This is fine because the solution is greatly optimised to `O(n^2)` 
- lets tabulate the results and take two dimensions where both dimension refer to the strings themselves . 
- At any given point of the tabulation we are faced with the problem of finding the longes common subsequence . If `text1[i]==text2[j]` then we are good and we don’t have to check anything we just have to update the table with `dp[i][j]=dp[i-1][j-1]+1` because it’s just the subsequence +1 without those characters in their respective strings . 
- If `text[i]!=text[j]` then it is just the `dp[i][j]=max(dp[i-1][j],dp[i][j-1])` , because the characters are not matching with each other anyways so it is better to step back and take the previous results . 


