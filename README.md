Thanks to https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase for the great overview!

This repository:

- starts from `master`
- **forks** into `branch-1`
- `master` is **rebased onto** `branch-1` 
  `branch-1` is merged back into master (-no-ff)

Result: **all commits from c1 to c10** appear in a straight line ( **git log** ) with a single merge commit

Possible improvement: rebasing `branch-1` into `master` instead of merge

### Git rebase interactive and squashing

git rebase `interactive` seems a good approach to cherry-pick multiple commits, e.g. when a subset of commits 
from a> previous merge caused issues. If we don't need the commit information we can **Squash** them!