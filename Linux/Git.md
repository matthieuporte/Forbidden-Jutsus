

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

### `git init`

When you run `git init` in a directory, Git sets up the necessary data structures and files to begin tracking changes in that directory.

---

### `git revert`

The `git revert` command is used to create a new commit that undoes the changes made in a previous commit. Unlike `git reset`, which modifies the commit history by moving the branch pointer, `git revert` is a safer option because it doesn't alter the existing commit history. Instead, it adds a new commit that undoes the changes made in a specific commit.
```bash
git revert <commit>
```


>[!abstract]- Tutorial
>1. **Identify the Commit to Revert:**
>   First, use `git log` to identify the commit that you want to revert. Note the commit hash or commit reference.
>
>     ```bash
>     git log
>     ```
>
>2. **Perform the Revert:**
>    Use the `git revert` command to create a new commit that undoes the changes introduced by a specific commit. Specify the commit hash or commit reference that you want to revert.
>
>     ```bash
>     git revert <commit>
>     ```
>   This command creates a new commit with changes that are the opposite of those introduced in the specified commit. The original commit is not removed or altered in any way.
>   <br>
>
>3. **Resolve Conflicts (if any):**
>   If there are conflicts between the changes introduced by the commit you're reverting and changes in your current branch, Git will pause and ask you to resolve the conflicts before it can continue with the revert. You'll need to manually resolve these conflicts, add the resolved files, and continue the revert.
>   <br>
>
>4. **Commit the Revert:**
>   After resolving conflicts (if any), you need to commit the revert.
>
>     ```bash
>     git commit
>     ```
>   Git will automatically generate a commit message indicating that it's a revert of a specific commit.

You can also revert the last commit :

```shell
git revert HEAD 
```

Or revert the x last commits :
```shell
git revert HEAD~3...HEAD
```


---

### List and change git branch
```shell
git fetch
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

### `git stash`
The `stash` command is used to temporarily save changes in your working directory that are not ready to be committed but need to be set aside.

```shell
git stash 
git stash list
git stash pop # restore and deletes last stash
# this might create merge conflicts
```

---

### `git reset`
The basic `git reset` command is used to reset the current branch pointer to a specified commit. It can be used in different modes:

>[!abstract]- **Soft Reset (`git reset --soft`):**
> This mode resets the branch pointer but leaves the changes in your working directory and staging area intact. The changes that were in the latest commit become staged (index), and you can modify them or commit them again.
>
>    ```bash
>    git reset --soft <commit>
>    ```

>[!abstract]- **Mixed Reset (default):**
>If you don't specify a mode, it performs a mixed reset by default. This resets the branch pointer and the staging area but leaves the changes in your working directory.
>
>    ```bash
>    git reset <commit>
>    ```

>[!abstract]- **Hard Reset (`git reset --hard`):**
>This mode resets the branch pointer, the staging area, and discards all changes in your working directory. It essentially reverts your working directory to the state of the specified commit.
>
>    ```bash
>    git reset --hard <commit>
>    ```
>    **Note:** Be careful when using `git reset --hard` as it discards changes in your working directory, and these changes cannot be easily recovered.


---

### `git clean`
The `git clean` command is used to remove untracked files from your working directory.

```bash
git clean -n #dry run
git clean -f 
git clean -fd #deletes in sub dirs as well
```
