
### Background
Dynamic programming is a technique of problem solving where the problem as a whole is broken down into sub problems which are logically referenced to compute the bigger problem . Dynamic programming is the single most differentiating factor in a programming interview . It one of the most obvious questions in the coding round . 


### Ways to Solve 

- **Tabulation** - Tabulation is a common technique and most taught methodology to solve dynamic programming . It is basically storing the pre-computed values of the sub-problems in arrays and these values are referenced when computing the bigger problem . 
- **recursive cacheing** - Recursive cacheing is when the sub-problems are stored in cache form while recursively computing . This is nothing but backtracking in a more systematic manner to avoid wasting time on repeated computations . 
- **Fenwick Tree and Binary Search** - This is an advanced technique used to solve dynamic programming problems . Fenwick tree is a range query data structure which is also used to compute and store the results of the sub-problems but I am unsure as to how this exactly works . 


### Dimensions 
I personally would like to use tabulation method often which is why I would like to look at this from the point of view of dimensions . Dimensions are basically how many different sub-problems is the main sub-problems branching out into . 
- **One Dimension** - One Dimension problems are the easiest from of dynamic programming problems where we just have to look back at one previous sub-problem of the same kind and these are usually rated as easy on leetcode . Some of these one dimension problems include-
	- [[Coin Change]] [[Coin Change problem]]
	- [[House Robber]]
- **Two Dimension** -Two dimensions problems are the ones that are more frequently used asked in interviews are the are rated medium on leetcode . Two dimensional dynamic programming problems basically branch two different decisions all together . 
	- [[Coin Change II]]
	- [[Longest Common Subsequence]]
- **Multi-Dimesnion** - This is when the sub-problems decision branch into multiple states of sub-problems . These are very hard problems to solve . They are asked only if you are interviewing for the top most of positions . 


