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


#restore file
```
git restore <filename>
git checkout -- <filename>
```

#check update
```
git fetch
git log origin/master
```

#pretty log
```
git log --oneline --decorate --graph
git log --decorate --graph --abbrev-commit --date=relative
```

# discard change

## track file

git checkout -- .

## untrack file
Show what will be discarded
```
$ git clean -n
```

Then delete it
```
$ git clean -f
-f, file
-d, directory
-n, --dry-run
```

# Github clone sub directory
git --filter is complicated
and github doesn't open this options on their git server for that

# git vs svn
git allow you to have local copy and work locally until you push to change the remote
svn cannot have access to tree locally without tool like svk
There is a bridge that developers use git to push to centralize SVN repo

e.g. To download https://github.com/opencv/opencv/tree/master/samples/data
change tree/master to trunk , and checkout=clone in svn
```
$ svn checkout https://github.com/opencv/opencv/trunk/samples/data
```

# check remote branch
```
git remote add origin <remote reference>
git fetch
git log origin/master
```
```
git diff HEAD..origin/master --stat 
git stash --include-untrack save <name>
```


Moving commit
-------------
```
master A - B - C - D - E`

to

newbranch     C - D - E
             /
master A - B 

git reset --keep HEAD~3
git checkout -t -b newbranch
git cherry-pick ..HEAD@{2}
```
