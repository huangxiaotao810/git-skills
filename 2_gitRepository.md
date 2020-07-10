### 工作区、暂存区和本地库的介绍

* 工作区： 在电脑当前位置所能看到的文件夹或目录
* 暂存区： 一般存放在 ".git目录下" 下的index文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）
* 本地库： 工作区有一个隐藏目录.git，这个不算工作区，而是Git的版本库。

![介绍](http://www.myexception.cn/img/2015/05/29/1608401176.jpg)



### 工作区提交文件到暂存区

```bash
$ git add fileName
```

可选参数：

- `git add --all` 表示添加所有内容 
- `git add .` 表示添加改动文件（新文件和编辑后的文件）不包括删除的文件
- `git add -u` 表示添加编辑后的文件和删除的文件，但不包括新添加的文件



### 查看提交状态

```bash
$ git status
```

输入命令，自己观察输出结果的变化


### 查看本次修改内容
`git show`


### 暂存区提交文件到本地库

```bash
$ git commit -m "描述信息" fileName    (单个文件)
$ git commit -m "描述信息"             (多个文件)
```



### 查看修改内容

- `git diff` 查看工作区和暂存区的区别
- `git diff --cached` 查看暂存区和当前分支的区别
- `git diff HEAD -- fileName` 查看工作区与本地库最新版的区别



### 撤回本地库文件到暂存区

```bash
查看版本记录:
$ git log | less (推荐使用)
$ git log --pretty=online
$ git log --oneline
$ git reflog (推荐使用)

撤回操作：
$ git reset --hard 版本记录ID (推荐使用)
$ git reset --hard HEAD^^ (^^: 表示向前回滚两次， 1次/^)
$ git reset --hard HEAD~3 (~3: 表示向前回滚三次)
```

**输入命令，自己观察输出结果的变化。**



### 撤回暂存区到工作区的修改

```bash
$ git checkout -- <file>
```

根据实际情况，与`git reset --hard 版本记录ID` 命令搭配使用，效果更佳。



### 删除暂存区的文件

```bash
$ git rm --cached fileName
```



### 恢复暂存区的文件

```bash
$ git restore --staged fileName
```



### 删除文件

```bash
$ git rm fileName
<==> 等价于以下两步：
	$ rm fileName
	$ git add fileName
```



### 删除文件解释

**恢复 `rm readme.md` 误删？**
- 从暂存区拉取文件进行恢复`git checkout -- readme.md` 

**恢复`git rm readme.md误删？**

- 从本地库拉取文件恢复

```bash
$ git reset HEAD readme.md
$ git checkout -- readme.md
```

**删除本地库文件**

```bash
$ git rm readme.md
$ git add .
$ git commit -m "delete readme.md"
```



### 查看本地库已存放的文件

```bash
$ git ls-files
```


















