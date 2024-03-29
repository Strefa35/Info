## Git docs
    https://wiki.openstack.org/wiki/GitCommitMessages
    https://chris.beams.io/posts/git-commit/

## A new repo from scratch

    mkdir project
    cd project
    git init
    < Write some code >
    git add *
    git commit

## A new repo from an existing project

    cd project
    git init
    git add *
    git commit

## git clone

    # Clone project from GitHub
    git clone git@github.com:<user>/project.git

    # Initialize, update or inspect submodules
    git submodule update --init --recursive

## git push 

    git remote add origin https://github.com/<user>/project.git
    git push -u origin master

## Git merge
  https://www.atlassian.com/git/tutorials/using-branches/git-merge

    go to master-r1 or master 
    git pull - into master-r1 or master branch
    go to my-branch branch 
    git merge master-r1 or git merge master


## Git log
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


## Git stash

    git stash
    git stash pop
    git stash push -m "Comments"
    git stash list
    git stash pop
    git stash apply stash@{1}
    git stash pop stash@{1}
    git stash drop stash@{0}
    git stash clear 
    git stash branch branch-name


## Git branch

    git branch
    git branch branch-name
    git checkout branch-name
    git push -u origin branch-name

    git branch -D branch-name


# Git useful commands

    git reset --hard origin/master
    git clean -dfx


## Remove last commit from local & remote
    git reset --hard HEAD^
    git push origin -f


## Git rebase
    git rebase master
    git rebase origin/master


## Git push

    git push origin HEAD:refs/for/master
    git push origin HEAD:refs/for/stable-1.0


## Git cherry-pick

    git cherry-pick <number>


## Git checkout

    git rev-list -n 1 --before="2016-10-07 1:00" origin/master
    git checkout `git rev-list -n 1 --before="2016-10-07 1:00" origin/master`

## Undoing changes

### Working directory

    git checkout -- file.txt
    git checkout .
    git checkout clean -xdf

### Staging area (Index)

    git reset -- files.txt

### Local branch

    git reset HEAD^^ (HEAD~2)
    git commit --amend -m "Commit message"

### Remote repository

    git revert <sha1>

# git server
    https://git-scm.com/book/en/v2/Git-on-the-Server-Setting-Up-the-Server

    sudo useradd -m -r -U -d /home/git-repos git
    # or  sudo su - git

    su git

    mkdir .ssh && chmod 700 .ssh
    touch .ssh/authorized_keys && chmod 600 .ssh/authorized_keys

