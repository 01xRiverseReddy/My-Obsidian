
- We initially need to have an account or some form of credentials on the cloud platform .

- When change directories to the folder that has git initialised and we link our local repository to the cloud through the following command . `git remote add origin https:xyz-yadayayayda` 
- To break this command up .`git remote` is the specific command to perform operations the online repository to our local repository . The `add` command is to add a new online repository and `origin` is just the name assigned to the online repository as per best practices . It could be any name . 
- After adding the desired online repository to our local git . We push the code using the command `git push origin master`.
- To break this command down , `git push` is the command to push code to an online repository , `origin` here is the name of the online repository that we have stored in our local git . `master` is the name of the branch that we are trying to push . If we run git history and take a look at the graph we can see the master branch holding up . 
- When we run git push , all the commits of a branch are pushed to the online repository . #yelllow
- Git push only pushes commits . The git log will show which commit corresponds to what is present in the online repository by adding a flag `origin\master` in history . 
- If there are no new commits to push then git push is useless , it will not push anything . If commit branches from `origin\master` , you cannot do a git push . If you need to do one then use  `-f ` flag in the push command . 
- Let’s say another developer has performed some changes and pushed it to the online repository , your own local repo would not have the accurate state of the project . To update your local repo run `git fetch` and you local repo will be updated . 
- To get sync the branch changes to your local repository , we use `git pull` .