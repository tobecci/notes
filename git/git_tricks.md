# Git tips and tricks

## fetching from git

git fetch <remote-repo> <remote-branch>:<local-branch>
git checkout <local-branch>

## how to remove a file from git

* `git rm -r --cached [file name]`


## make git never ask for username and password
`git config --global credential.helper store`

## delete file from commit tree

git filter-branch -f --tree-filter 'rm -f /path/to/file' HEAD --all
