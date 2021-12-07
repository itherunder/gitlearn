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
$ git fetch origin main(git fetch <远程服务器名> <远程分支名>(不要这个的话会把remote所有的分支全部拉下来))
$ git merge FETCH_HEAD origin/main(git merge <HEAD> <分支名>)
```
git fetch <远程服务器名>，该命令只会将数据下载到你的本地仓库——它并不会自动合并或修改你当前的工作，当准备好时你必须手动将其合并进入你的工作
git push -u(这次的<remote> <branch>将会是以后的默认，之后git push 不用再次输入<remote> <branch>) <remote> <branch>，只有当你有所克隆服务器的写入权限，并且之前没有人推送过时，这条命令才能生效。 当你和其他人在同一时间克隆，他们先推送到上游然后你再推送到上游，你的推送就会毫无疑问地被拒绝。 你必须先抓取他们的工作并将其合并进你的工作后才能推送。
git remote show <remote>，它同样会列出远程仓库的 URL 与跟踪分支的信息。 这些信息非常有用，它告诉你正处于 main 分支，并且如果运行 git pull， 就会抓取所有的远程引用，然后将远程 main 分支合并到本地 main 分支。 它也会列出拉取到的所有远程引用。

