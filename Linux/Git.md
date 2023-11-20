

### Config SSH keys
```shell
ssh-keygen -t ed25519 -C "your_email@example.com"
```

then put your public key online
the keys are usually stored in ~/.ssh

---

### Different methods to connect to a git repo :
```
ssh://[user@]host.xz[:port]/path/to/repo.git/
git://host.xz[:port]/path/to/repo.git/
http[s]://host.xz[:port]/path/to/repo.git/
ftp[s]://host.xz[:port]/path/to/repo.git/
```

---

### Go back in git logs
```shell
git revert HEAD # will create a new commit doing the opposite of the last commit
git revert HEAD~3...HEAD # revert the last three commits
```

>[!tip]
>you can git revert twice in a row to go back to the original state

---

### List and change git branch
```shell
git fetch #
git branch #list all local branhes
git branch -a #list all branches (-r to only list remote)
git checkout mybranch #change branch
```

---

### List all tags
```shell
git tag -l
# go to the commit of the tag in a new branch
git checkout tags/[tagname] -b mybranch
# show information about the tag itself
git show [tagname]
```

---

### git stash
```shell
git stash 
git stash list
git stash pop # may create git conflicts
```

---

### Go back to a certain commit without committing again

First, update all `origin/<branch>` refs to latest:

```bash
git fetch --all
```

Backup your current branch (e.g. `master`):

```
git branch backup-master
```

Jump to the latest commit on `origin/master` and checkout those files:

```
git reset --hard origin/master
```

#### Explanation:

`git fetch` downloads the latest from remote without trying to merge or rebase anything.

`git reset` resets the master branch to what you just fetched. The `--hard` option changes all the files in your working tree to match the files in `origin/master`.
