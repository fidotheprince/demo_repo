## Review this file when ever you get rusty

* Below is just a bit of chicken scratch for practice
* I'm refreshing my version controll skills
* Note all changes to your local branch are recorded via the hidden .git file

1. HTML is important. 
```html
<p> This is test HTML </p>
```
2. JavaScript is important. 
```js
  console.log('Hello World');
```

* Here are some common git commands 
  ---
  * `git status` enables you to see what changes (in your files) have been tracked, and which have not
  * `git add` <filename> enables git to start tracking changes to files 
  * `git add <file>` is saying, "git look at changes made on this file"
  * `git add .` track changes in all the files within this directory"
  * `git commit -m"random message here;"` is how you designate changed files that you'd liked merged
    * add a second `-m""` to write text for the description of your commit
  * `git branch` shows what branch you're on 
  * `git push origin main` tells git where to merge to

* How to turn a local project into a remote git repository 
  ---
  * `git init` initializes a local directory as git repository 
    * Run this command within project folder
  * Create a new empty repository on GitHub
    * Copy provided HTTPS link for repository
  * Connect local repo with the remote repository
    * Run the following command within your projects directory
    * `git remote add origin httpslink@.com:goeshere`
  * Check remote repos that you've connected to via this commmand
    * `git remote -v`

* Git branching
---
  * Master or Main is the naming convention for the principle branch
  * What happens when you work through a branch
    * At checkout, both parent and child branches are the same
    * As you push changes to your child branch updates will only be made on this branch
    * The branches don't have a way of knowing what changes have been made to another branch
      * Isolated branches while you work on the code can prevent breaking changes to master
      * You only merge your branch back to master (the parent) when you know it works
    * You can also do a HOTFIX (child branch) where you checkout a branch
      * Fix the code, and merge the branch back into master(parent branch)
  * To create a new branch of parent use `git checkout -b descriptivenamehere-11`
  * To switch between branches use `git checkout branchNameHere`
  * To see changes you'll commit use `git diff` command

* How to merge a checked out branch to main (parent branch)
---
  * Make sure to have a remote branch to be pushing too 
    * To define the remote branch you'll be pushing to 'git push --set-upstream origin feature-branch-AC12'
  * Sets up a _Pull Request_ to merge child branch to parent branch
    * PR originates from child branch
    * Code reviews are best done prior having a child branch merged
    * You can continue to update the child branch even while it has a live pull request
      * No been merge has been approved yet, so you're gucc to keep tweaking as needed
  * Once PR is merged you'll can delete the local child branch & switch back to master
  * The owner of a repo will see that you just pushed to your branch and open a PR
    * This is done through GitHub's graphical UI
    * There are several review tools, including code comments that you can use to live PR request
  * To delete a branch use this command `git branch -d branch-name-here`

* How to get the most recent changes to your master (parent) branch
---
  * `git pull origin master` to recieve the most recent changes to the code

* Handling Merge conflicts
---
  * To add and commit a modified file at the same time use `git commit -am "random message here"`
  * The key with handling merge conflicts is literally to overview them manually
  * VScode gives you great visual tools to do this

  * If you ever want to undo a `git add <filename>` command 
    * E.g to unstage a file, use this command `git reset <filename>`
  * If you ever want to reset a commit do the following
    * `get reset HEAD~1`
    * _HEAD_ is a pointer to the list of commits 
    * _~1_ is saying go back to commit before the mess up
      * E.g undo the commit you just made
  * To see a log of all of your commits use `git log`
    * The log is organized from latest commit to earliest
    * To recent form a specific point forward user 
      * `git reset 40a0ac562a932b4d407a4d286e35fde1634be61c` the wierd text is a commit hash
      * It resent that commit and any commits that came after it
