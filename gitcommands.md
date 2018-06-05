# Git Commands

## Reference 

https://docs.oracle.com/en/cloud/paas/developer-cloud/csdcs/using-git-command-line-interface.html#GUID-3F782579-50B6-4CCA-AD1C-D7E508D73974


## Set up a new repository using the command line

    git clone <url>
    cd <dir>
    touch README.md
    git add -A .
    git commit -m "Initial commit"
    git push -u origin master

## Add a new remote repo and populate it

    git remote add <repo name, e.g. origin> <url>
    git push -u origin master


## Display local repos links to remote

    git remote show 
    git remote show <repo name>

## Remove file from a repo:

    git rm <filename>
    git commit
    git push

## Change the remote repo
git remote set-url origin git@github.com:username/repo.git


## Download a single file like this:

    wget https://raw.githubusercontent.com/jquery/jquery/master/src/ajax.js

## Avoid need to put username/password when doing "git push"

    Edit ~/.netrc
    Enter "machine <domain, e.g. github.com> login <user> password <pw>" 