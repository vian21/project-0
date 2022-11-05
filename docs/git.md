# Using Git

**Author**: Patrick Igiraneza  
**Date**: November 5, 2022

## git clone

Git clone is used to copy an online repository to your computer. You can git clone using the github link(HTTPS), using SSH or just download a zip directly from Github.

```sh
git clone https://github.com/vian21/project-0
```

## Updating a branch (git pull)

Git pull is using to update your local branch with the online one. You do this to see to see if there has been some changed on the branch i.e someone has pushed code on it.

```sh
git pull
```

## Creating a branch (git checkout)

Branches help us prevent merge conflicts which arise when two people work on the same thing and have different code. Github will not know which one to keep or discard. Branches allow one to work on a feature without actually breaking the project. `DON'T WORK ON THE MAIN BRANCH!!!`.

TO create a new branch:

```sh
git checkout -b branchName
```

- checkout : tells git to change the current branch to the specified branch
- `-b` : tells git to create a new branch. Don't include it if that branch already exists.

## Changing branch (git checkout)

Git checkout allows you to change branch and see what other branch contain. You can switch from your branch to the `main` branch or somebody else's to see what they are working then you can `git pull` to update your local copy of the branch.

```sh
# git checkout branchName
git checkout main # switch to the main branch
```

## MERGING

NOTE: Merging is done on the main branch

### 1. Commit & Push to your branch

```sh
git add .
git commit -m "commit message(REQUIRED)"
git push
```

### 2. Update your local main branch

```sh
git checkout main
git pull
```

### 3. Merge your branch with the main branch 💀

This is where the 'magic' happens.

```sh
git merge branchName
```

### 4. Resolve conflicts (Not always)

Git will automatically try to merge the two branch and notify you if there are conflicts it can not resolve by its own. That is where you come in.

Try and resolve all the merge conflicts by either:

- Accepting both changes
- keeping the other persons code or Keeping only your if it is the latest or an update/refactor.

#### Merge again

After resolving all the conflicts, try merging again your branch into the master branch.

### 5. Create a Pull request

After successfully, merging the two branch. Go to the repository on Github. Git hub will suggest you to create a pull request.

- Create a pull request
- Add a small message describing what you changed (added and removed)

If it was a minor change you can directly merge the pull request yourself or wait for your repo manager review the code first and approve your changes.

The manager will either merge your pull request or give you an OK to merge the PR yourself.

## Additional

### Updating your branch with what is in the main branch

```sh
git checkout main         # go to the main branch
git pull                  # update it
git checkout branchName   # go back to your branch
git merge master          # merge the latest main into your
```
