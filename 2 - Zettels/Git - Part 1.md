
### Overview
	
- Git is command-line version control software tool for us to maintain different versions of our code so that we can travel back and work on them . 
- The key use-case of Git is that it lets. Multiple developers work on a single codebase without overwriting each others work . 
- Git is by-far the most famous and probably the only version control tool in the market and is a mandatory skill to be employed in high paying jobs . 



### Commits 

- Commits is the way a developer saves a set of changes to the history of the codebase . 
- Commits can be defined as checkpoints in a codebase. 
- Each commit links to the other commit in a single straight line to establish a unidirectional relationship.
- Each commit has a hash associated with it so that it is uniquely identified . In addition you can have a message associated to it to describe it . 
![[IMG_0013.jpeg]]


### Branching  and Merging 

- Branching is the strategy used by the developer to isolate his work and perform changes . 
- Git branching creates a new path of commits creating a bidirectional pathway for commits . 
- `git branch <branch-name>` is the commit to create a new branch . 
- Merging is the process or procedure you follow when you want to have your line of work pushed to the main repository/ have your changes int he production . 
- The command for this `git merge <branch-name>` . Git merge the branch mentioned to your current branch. 
- **Which is why always checkout the main branch and then merge it with the feature branch** 

### Moving Head

- HEAD is a pointer which indicates the current commit we are working on . We can always use the `git checkout <commit-name>` command to move around our commits . 
- You can move the head relatively using certain operands . 
- `git checkout main^`  the hat operand signifies that we need to take one commit prior to the main branch . We can use hat command to signify the look back of commits for example `git commit main^^` , the number hats signify the look back . In this case two . 
- Using the hat operand might be inconvenient , which is why the tilde operand was introduced . With the tilde operand you can directly signify the number of look backs . `git checkout main~3` . 


### Git reset and git revert

- Git reset is a command that is used to undo changes . Git reset literally take the most recent commit prunes it from the tree . This command is excellent and works efficiently when the changes are only on our local repo but if the changes are on the remote repository as well , then the effects can be dangerous as it is irreversible . 
- Git revert was designed for taking remote repository into consideration  . What git revert does it takes the previous commit (which is essentially the undone version of the current commit ) and creates a commit on top the recent commit without making irreversible changes to the tree . 


### Git cherry picking and interactive rebasing 

- Git cherry-picking is the command used for copying commits and adding on top of the HEAD pointer . The command is `git cherry-pick <commit-name> <commit-name>` 
- Git interactive rebasing lets us choose the look back scope , re-order the commits and provide a small graphical user interface to do this. 
- The command for this is `git reset -I HEAD~3` . In the previous commit we have a look back period of 3 which means that our head will move 3 commits back and then let’s us pick-and re-order from these 3 commits . 



### Moving around with commits 

- Moving commits around is done mainly with these two commands `git cherry-pick` and `git rebase` . 
- We can change the entire meaning of commit trees using these two commands , whether it is positioning or rebasing . 


### Git Reset vs Git Revert


Literature : [[Learn Git Branching online - Main]]
