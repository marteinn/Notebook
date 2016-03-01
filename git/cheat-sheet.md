# Git - Cheat Sheet

## Commits

#### Show commits
`git log`

#### Show patch
`git log -p`

#### Show diffstat
`git log --stat`

#### Show commits from specific user
`git log --author=[username]`

#### Shorter status
`git status -s`


## Branches

#### Create branch
`git checkout -b mybranch`

#### Merge branch
`git merge mybranch`

#### Show branches
`git branch`

#### Create branch
`git branch [branch]`

#### Show branches and latest commit
`git branch -v`

#### Delete branch
`git branch -d [branch]`

#### Delete remote branch
`git push origin --delete [branch]`

#### Create branch and perform checkout
`git checkout -b [branch]`

#### Get all branches
`git fetch --all`

#### Push and remove local branch
`git push origin :[branch] `


## Tags

#### Show all tags
`git tag`

#### Show all tags with a description
`git tag -n`

#### Search for tags
`git tag -l "[tagname]*"`

#### Show tag info
`git show [tagname]`

#### Create tag with message
`git tag -a [tagname] -m "message"`

#### Create tag
`git push origin [tagname]`

#### Push all tags
`git push --tags`

#### Pull all remote tags
`git fetch --tags`

#### Delete tag
`git tag -d [tagname]`

#### Delete all local tags
`git tag | xargs git tag -d`

#### Delete remote tag
`git push origin :refs/tags/[tagname]`


## Commits

#### Show latest commit
`git rev-parse HEAD`

#### Show latest commit in short format
`git rev-parse --short HEAD`


## Ignore

#### Ignore untracked file locally
`echo "setup_mysql_headers.sh" >> .git/info/untracked`


## File

#### Reset file
`git checkout [filename]`

#### Unstage file, but keep changes
`git reset HEAD [filename]`

#### Remote from history
```
git filter-branch --force --index-filter \
'git rm --cached --ignore-unmatch [filename]' \
--prune-empty --tag-name-filter cat -- --all
```

