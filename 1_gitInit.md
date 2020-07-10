### 配置git用户名和邮箱

```bash
$ git config --global user.name "用户名"
$ git config --global user.email "邮箱地址"
```

注： 在`config` 后加上`--global`参数，可以全局设置用户名和邮箱， 如果不加，则针对的局部设置（对本仓库有效）

### 生成密钥`ssh key`

```bash
$ ssh-keygen -t rsa -C "邮箱"
```
按3个回车，密码为空。

然后根据提示连续回车即可在~/.ssh目录下得到id_rsa和id_rsa.pub两个文件，id_rsa.pub文件里存放的就是我们要使用的key。

### 上传key到github

```bash
$ clip < ~/.ssh/id_rsa.pub
```

复制key到剪贴板;  登录github;  点击右上方的Accounting settings图标; 选择 SSH key;  点击 Add SSH key



### 测试是否配置成功

```bash
$ ssh -T git@github.com
```

如果配置成功，则会显示： ***successfully authenticated***.



### 本地仓库的创建

```bash
$ git init
```

执行该命令后，会自动生成隐藏文件夹`.git`

