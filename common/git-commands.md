# Git Commands

## Docs

- <https://wiki.openstack.org/wiki/GitCommitMessages>
- <https://chris.beams.io/posts/git-commit/>

## New repo from scratch

```bash
mkdir project && cd project
git init
git add .
git commit
```

## New repo from an existing project

```bash
cd project
git init
git add .
git commit
```

## git clone

```bash
# Clone project from GitHub
git clone git@github.com:<user>/project.git

# Initialize, update or inspect submodules
git submodule update --init --recursive
```

## git push

```bash
git remote add origin https://github.com/<user>/project.git
git push -u origin master
```

## Git merge

Reference: <https://www.atlassian.com/git/tutorials/using-branches/git-merge>

```bash
git checkout master          # or master-r1
git pull
git checkout my-branch
git merge master             # or git merge master-r1
```

## Git log

```bash
git log --oneline
git log --author="Arkadiusz"
git log --oneline --author="Arkadiusz"
git log --grep="added"
git log --oneline -3
git log --oneline -- readme.md
git log --oneline --patch -- readme.md
git log --oneline --summary
git log --oneline --stat

git log --graph --decorate --all --oneline

git shortlog
git shortlog --author="Arkadiusz"
```

## Git stash

```bash
git stash
git stash pop
git stash push -m "Comments"
git stash list
git stash apply stash@{1}
git stash pop stash@{1}
git stash drop stash@{0}
git stash clear
git stash branch branch-name
```

## Git branch

```bash
git branch
git branch branch-name
git checkout branch-name
git push -u origin branch-name

git branch -D branch-name
```

## Useful commands

```bash
git reset --hard origin/master
git clean -dfx
```

## Remove last commit from local & remote

```bash
git reset --hard HEAD^
git push origin -f
```

## Git rebase

```bash
git rebase master
git rebase origin/master
```

## Git push to Gerrit

```bash
git push origin HEAD:refs/for/master
git push origin HEAD:refs/for/stable-1.0
```

## Git cherry-pick

```bash
git cherry-pick <commit-hash>
```

## Git checkout at a point in time

```bash
git checkout `git rev-list -n 1 --before="2016-10-07 1:00" origin/master`
```

## Undoing changes

### Working directory

```bash
git checkout -- file.txt
git checkout .
git clean -xdf
```

### Staging area (Index)

```bash
git reset -- files.txt
```

### Local branch

```bash
git reset HEAD^^          # same as HEAD~2
git commit --amend -m "Commit message"
```

### Remote repository

```bash
git revert <sha1>
```

## Git server setup

Reference: <https://git-scm.com/book/en/v2/Git-on-the-Server-Setting-Up-the-Server>

```bash
sudo useradd -m -r -U -d /home/git-repos git
su git

mkdir .ssh && chmod 700 .ssh
touch .ssh/authorized_keys && chmod 600 .ssh/authorized_keys
```
