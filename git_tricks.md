# Git tips and tricks

## fetching from git

git fetch <remote-repo> <remote-branch>:<local-branch>
git checkout <local-branch>

## when gitignore or exclude is not working

* `git rm -r --cached .`

## make git never ask for usename and password
`git config --global credential.helper store`