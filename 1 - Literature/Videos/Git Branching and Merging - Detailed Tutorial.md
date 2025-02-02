

### Branching 

- Git branching is the tool / method used to isolate work from the code that is supposed be active in production . 
- The syntax for git branching is pretty straight forward . `git branch branchName ` . This creates a branch on whichever commit the head branch is on .
- After creating the branch . The head branch needs to be changed to the branch in order to work with it . Can be done using the checkout command . 
- You can Keep making commits on top of the branch and push those commands using the push command to the online repository . 


### Merging 

- Merging is the mechanism/ tool used to combine the changes that or are on a branch to another commit , usually the master branch . 
- The syntax for merging is  `git merge branchName`. Here branch name refers to the name of the branch that merge with the current head pointer . 
- Git merge always happens on the branch that is pointing to the head . Therefore as best practice the head should always be on the master branch when merging .


### Merge Conflicts 

- Merge conflict is a type protective barrier that shields the git branch from getting from overwriting changes that have been made by other developers . 
- When two developers change the same line of code , git detects and asks the developer to double confirm before merging the changes to main branch . 

