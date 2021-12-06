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
git commit --amend: 用来在commit之后发现commit信息写错了
如果发现少添加了文件或者啥的，如下操作：
```bash
$ git commit -m 'initial commit'
$ git add forgotten_file
$ git commit --amend
```
最终你只会有一个提交——第二次提交将代替第一次提交的结果。
git reset HEAD <file>...: 取消暂存(从staged->untracked or modified(before status))，还不知道和git restore --staged 有什么区别（git reset是一个很危险的操作，特别是加上--hard之后）
git checkout -- <file>...: 取消某个文件的修改（modified->unmodified），回将这个文件替代成最近提交的这个file，而且不会有备份，属于是无法撤销的撤销

## 远程仓库
![git structure](./pictures/git_structure.jpg)
git remote(查看远程仓库的服务器) -v(查看url)
git remote add <shortname> <url>(手动添加远程仓库，clone可以自行添加远程仓库)
example:
```bash
$ git remote add origin https://github.com/itherunder/gitlearn
$ git pull origin main:main(git pull <远程服务器名(就是git remote -v的结果)> <远程分支名>:<本地分支名>)
#也可以使用fetch + merge，和pull 是一样的
$ git fetch origin main(git fetch <远程服务器名> <远程分支名>)
$ git merge FETCH_HEAD origin/main(git merge <HEAD> <分支名>)
```
