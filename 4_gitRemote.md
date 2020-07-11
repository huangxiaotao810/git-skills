## 远程仓库



### 克隆仓库

```bash
$ git clone https://github.com/huangxiaotao810/git-skills.git
```



### 查看仓库

```bash
$ git remote -v
```



### 关联仓库

```bash
$ git remote add origin https://github.com/huangxiaotao810/git-skills.git
```



### 取消关联仓库

```bash
$ git remote remove origin
```



### 推送到仓库

```bash
$ git push origin <branch-name>
$ git push -u origin <branch-name> `
-u` 意同 --set-upstream，用以将本地库分支与远程库分支关联
```



### 拉取到本地仓库

```bash
$ git fetch origin master
$ git checkout origin/master
$ git merge origin/master

OR (pull == fetch + merge)

$ git pull origin master
```

### 仓库的回滚

```bash
$ git reset --hard 版本ID
$ git add --all 
$ git commit -m "recovery"
$ git push -f origin master
```

**Tips: 对master分支进行操作时，由于master分支受保护，所以需要解除保护。（以gitlab为例）**

**解除步骤**
`打开gitlab项目页 -> Setting -> Repository -> Protected Branches`



### Create a new repository

```bash
$ git clone https://github.com/huangxiaotao810/git-skills.git
$ cd test
$ touch README.md
$ git add README.md
$ git commit -m "add README"
$ git push -u origin master
```



### Push an existing folder

```bash
$ cd existing_folder
$ git init
$ git remote add origin https://github.com/huangxiaotao810/git-skills.git
$ git add .
$ git commit -m "Initial commit"
$ git push -u origin master
```



### Push an existing Git repository

```bash
$ cd existing_repo
$ git remote rename origin old-origin
$ git remote add origin https://github.com/huangxiaotao810/git-skills.git
$ git push -u origin --all
$ git push -u origin --tags
```





