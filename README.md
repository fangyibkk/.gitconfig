# .gitconfig
My git tips and config file

Useful command
Seeing remote branch
```
$ git branch -r
```
Create new branch and pulling from remote
```
$ git checkout -t origin/that-remote-branch-name
or more modern
$ git checkout that-remote-branch-name
```
See what is tracking what before shorthand `git push` and `git pull`
```
$ git branch -vv
```

Change the branch name
```
$ git branch -m <old-name> <new-name>
```
Rebase and squash\
Note that you cannot squash the commit itself that you checkout to\
So checkout that `<commit-id> - 1`
```
$ git rebase -i <commit-id>
```
