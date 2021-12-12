## 分支学习
### 新建 & 切换分支
```bash
git branch branch-learn
git checkout branch-learn
git checkout -b(可以直接切换到这个新建的分支) branch-learn
```

### 删除分支
```bash
git branch -d hotfix(删除本地分支)
git push <remote> --delete <branch/tag> 还是用之前删除远程tag 的方式删除远程分支
```

### 合并分支
```bash
git merge branch-learn(可能会有conflicts，手动解决一下就行了)
# 也可以使用vscode 的git 插件，可以直接accept changes
# 上面这个git merge 其实会在当前这个分支有多个提交，这取决于要合并的分支`branch-learn`里面有多要个提交，都会全部合并过来并且再进行一次merge 的提交，即n+1 次commits
```

### 查看分支信息
```bash
git branch -v(显示每条分支的最后一次提交) -a(显示所有分支，包括远程的以及HEAD)
git branch --merged(或者--no-merged 可以查看哪些分支是合并/没有合并到当前分支的，已经合并了的可以直接删除分支而不会损失信息)
```
