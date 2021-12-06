
## second commit
all status: untracked -> tracked(unmodified -> modified) -> staged
git add: untracked or modified -> staged
git commit: staged -> unmodified
git del(restore --staged): staged -> untracked or modified(before status)
git reset --(git reset HEAD --): staged -> untracked or midified(before status)，似乎和上面的git del没啥区别
edit: untracked -> untracked | unmodified -> modified

## third commit
git diff: difference workspace and staged
git diff --staged: difference staged and last committed
git diff --cached: 和--staged一样

