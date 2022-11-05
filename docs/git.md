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
### 1. Update your local main branch
```sh
git checkout main
git pull
```
### 2. Merge your branch with the main branch 💀
This is where the 'magic' happens.
```sh
git merge branchName
```
### 3. Resolve conflicts
Git will automatically try to merge the two branch and notify you if there are conflicts it can not resolve by its own. That is where you come in 


