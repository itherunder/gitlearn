## git的状态
all status: untracked -> tracked(unmodified -> modified) -> staged
git add: untracked or modified -> staged
git commit: staged -> unmodified
git del(restore --staged): staged -> untracked or modified(before status)
git reset --(git reset HEAD --): staged -> untracked or midified(before status)，似乎和上面的git del没啥区别
edit: untracked -> untracked | unmodified -> modified

## 几个区的具体区别（更详细的status
git diff: difference workspace and staged
git diff --staged: difference staged and last committed
git diff --cached: 和--staged一样

## 查看提交历史
git log -p(查看详细diff) -2(查看最近两次的提交) --stat(每个历史提交的小总结) --since=2.weeks(最近两周的)

## 撤销
git commit --amend: 用来在commit之后发现少添加了文件或者commit信息写错了