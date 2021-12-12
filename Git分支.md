## 分支学习
### 新建 & 切换分支
```bash
git branch branch-learn
git checkout branch-learn
git checkout -b(可以直接切换到这个新建的分支) branch-learn
```

## 删除分支
```bash
git branch -d hotfix(删除本地分支)
git push <remote> --delete <branch/tag> 还是用之前删除远程tag 的方式删除远程分支
```

### 合并分支
```bash
git merge branch-learn(可能会有conflicts，手动解决一下就行了)
```