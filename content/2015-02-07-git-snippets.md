Title: Git Snippets
Date: 2015-02-07 13:11:08 -0600
Modified: 2015-02-07 13:11:08 -0600
Category: Programming
Tags: git

#### Sort branches by last commit
``` bash
git for-each-ref --sort=-committerdate --format='%(color:yellow)%(committerdate:short)%(color:reset) %(refname)' refs/heads refs/remotes
```
