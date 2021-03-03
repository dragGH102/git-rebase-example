Thanks to https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase for the great overview!

This repository:

- starts from `main`
- **forks** into `branch-1`
- `main` is **rebased onto** `branch-1`
- `branch-1` is merged back into master (-no-ff)

Result: **all commits from c1 to c10+** appear in a straight line ( **git log** ) with a single merge commit in `main`

Possible improvement: rebasing `branch-1` into `master` instead of merge

---

Commits list snapshot: ( `git log --pretty=oneline --abbrev-commit` )

__c12+ here__
- d62940d (HEAD -> main, origin/main) 11: fix typo
- 8a6906f (refs/bisect/skip-8a6906fa1ab814bf683e5fd9bbc26c350826af2c) c10: add README
- cf6acf5 Merge branch 'branch-1'
- d83bd34 (branch-1) c9 (branch-1): modify add-3
- 78cf4db c8 (branch-1): add and modify add-4
- b49aed3 c7: rename add-3 to mofify-3
- a09390f c6: add add-4
- 13b0517 c5: rename add-1 to modify-1
- d5120b9 c4: add add-3
- 39ddc5c c3 (branch-1): modify-add-1-without-rename
- cf29294 c2(branch-1): add add-2
- faa2f63 c1: add add-1


### Git rebase interactive and squashing

git rebase `interactive` seems a good approach to cherry-pick multiple commits, e.g. when a subset of commits 
from a> previous merge caused issues. If we don't need the commit information we can **Squash** them!
