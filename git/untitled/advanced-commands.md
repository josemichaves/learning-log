# Advanced Commands

```text
git reset <file>
```

Remove the file from the staging area, but keeps the worign area intact.



```text
git branch <branch-name>
```



Without the `<branch-name>`list all the branches in the repo. With the `<branch-name>`create a new branch with the name given in `<branch-name>`.



```text
git checkout -b <branch-name>
```

Change to the branch especified in `branch-name`, if the argument `-b` is used, will create the branch and change to it.



```text
git merge <branch>
```

Merge `<branch>`branch with the current branch. 



```text
git remote add <name> <url>    
```

Create a new connection to a remote repo. The `<name>` can be used as a shorcut for the url, and its the name of the added repo.



```text
git fetch <remote> <branch>
```

Download the copy in the repo, but doesn't merge with the local copy, instead of this shows in the working directory, but not changes are made.



```text
git pull <remote>
```

Download the copy in the repo and merge it with the local copy. It's replaces all the content in your working directory.



```text
git push <remote> <branch>
```

Send the `<branch>`to the remote along with all the commits and objetcs. It's like sending all the work to the repo.



