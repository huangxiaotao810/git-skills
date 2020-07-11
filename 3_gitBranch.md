### 常见分支命令

```bash
查看所有分支： $ git branch -a         注：   (all)

查看远程分支： $ git branch -r         注：   (remote)

创建分支： $ git branch branchName

切换分支： $ git checkout branchName

创建+切换分支: $ git checkout -b branchName

合并某分支到当前分支：$ git merge branchName

合并某分支到当前分支：
$ git merge --no-ff -m "description" branchName
`--no-ff`参数可以查看合并的作者和时间戳等信息

删除分支：$ git branch -d branchName

强制删除分支： $ git branch -D branchName

删除远程分支：
$ git push origin --delete branchName
OR
$ git push origin :branchName (origin后面有空格)

查看分支合并图: 
$ git log --graph 
$ git log --graph --pretty=oneline --abbrev-commit
```



### 贮藏与清理

```bash
保存stash: $ git stash
把所有未提交的修改（包括暂存的和非暂存的）都保存起来，用于后续恢复当前工作目录。

恢复stash: $ git stash pop

查看stash: $ git stash list

指定stash：$ git stash apply versionID

移除stash: $ git stash drop versionID

删除stash: $ git stash clear

区别stash: 
$ git stash show    注：后面可以跟着stash名字
$ git stash show -p

创建stash分支: $ git stash branch branchName
```

