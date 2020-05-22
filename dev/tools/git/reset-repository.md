# Reset Repository

## Links

- [Remove all history from a GitHub repository](https://freek.dev/1547-remove-all-history-from-a-github-repository)
- [Squash all Git commits with git squash-all](https://www.bram.us/2020/01/16/squash-all-git-commits-with-git-squash-all/)

## clone the repo (skip if you already have a cloned repo locally)
git clone git@github.com:USERNAME/REPOSITORY.git
cd REPOSITORY

## remove all history locally
rm -rf .git

## create a new local repo
git init

## add everything
git add .
git commit -m "First commit"

## nuke history on GitHub (irreversable)
git remote add origin git@github.com:USERNAME/REPOSITORY.git
git push -u --force origin master
