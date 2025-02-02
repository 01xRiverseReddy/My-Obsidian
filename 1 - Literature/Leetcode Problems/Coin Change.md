
https://leetcode.com/problems/coin-change/description/



### Brute / Greedy 

- The brute force would be to generate every possible combination of the coins and wait till we find the combination that would take the fewest coins . This would work under the scenario where the no. Of coins would be less than 100 but they are not and they could go up to 10^4 hence we run in into TLE . 
- Greedy approach would be to take the amount and divide with the highest denominations and repeat this process with the remainder . But the problem with this is that the coins do not always fit perfectly and the result is not always optimal . 



### Optimal Approach 

- We break the problem into sub-problems and ask our selves if the amount is 11 and we have denomination worth 3 . Then the number of coins to achieve the sum 11 would be the number of ways we can achieve the sum 8 plus 1 (adding the 3 denomination) . 
- This way we maintain a table to store the minimum coins we can use for each amount and we can have the sub-problem computed readily . 
- We use two loops one to iterate over every sum up till amount , while the other to iterate over every coin . This would take `O(n^2)` .