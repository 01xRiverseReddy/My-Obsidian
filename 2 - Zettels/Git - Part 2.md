
### Background 

- Having an online repo/source tracking in the era cloud computing is must solely for the reason that it provides a backup of your local git tree . Furthermore it helps you and other developers to work remotely in a collaborative manner . GitHub is by far the most popular online repository out there . 

### Cloning online Repo
- `git clone`  is the command used for making a copy of an online repository in your local machine . 
- when we clone remote repository , it shows up a special branch on the Git graph which the remote branch  . This is for us to help track the changes which are local and which are remote . 

### Origin/ main branch

- Origin/main branch is the branch that is tied main branch that is consistent across the commit tree for the online repository . 
- Whenever the Origin/main branch is checked out , the head is in a detached state . Which means even if you commit after checking the remote branch , the branch is not updated to the new commit . This is due to the special property that remote branches are only updated on the local repository in correspondence to the remote repository . 


### Git Fetching and pulling 
- `git fetch` this command essentially asks the local repository what changes from the online repository are not updated on my local repo and update them .  So any new commits or branches will show up on your local . 
- Key notable thing is that let’s say you yourself have made commits that are not on the online repository . Then when you run git fetch all the commits that come forth will form a fresh branch. 
- Git pull is a special command this is a conjunction of git fetch and git merge origin/main . Ideally whenever you perform git fetch you would wan’t to merge your local main with origin/main to keep the sync . What git pull does is , it performs both commands together . 

### Git Push 
- Git push is the command we use to move our changes from local repository to the remote repo . Git push is a very erroneous command due to fact that there is ambiguity with the remote branch . For instance , if there are active changes being pushed to the remote repo and all of a sudden you wish to push your changes to the repo , your local branch and remote branch are way out of sync for you to push changes . In cases like this we need to first update our local repo through a command like git fetch , then merge/rebase our main branch with o/main  . Then we push the new updated commit to the online repository . 
- If we have a specific feature branch we push it to the online repo for global tracking using `git push origin feature `  . 
- There is a specific case where , let’s say we are working on a feature on Monday and we finish by Friday and we are ready to push but the problem is that a lot of code has been added to the repository since Monday . Running git push is ambiguous hence it would simply fail . In this case we first run `git fetch `  then we check to see where o/main is relative to main and then merge / rebase local main with o/main . After our changes are ready we would be good to push . 

### Main branch being locked out 

- Main branch being locked is almost every organisation’s policy out there to prevent accidental overwriting / unrevised code running in the production . 
- Which is why pull requests have come into place for such scenarios . Pull requests are changes reviewed by other peers before they are merged onto the main branch . 
- In such scenarios you push the feature branch to the online repository using the command `git push origin ` and when you reach the online repository you raise a pull request to merge the feature branch to the main . 




Literature :[[Lean git Branching online - part 2]]