# git学习笔记

## 本地仓库创建

首先在windowns平台或linux平台安装git工具,linux平台通过命令行安装，linux平台通过官网下载git工具安装。

在文件夹的位置，鼠标右键选择git bash here，输入 git init命令，在文件夹内会多一个.git的文件夹

```shell
sudo apt install git #linux平台安装git命令
git init #初始化git本地仓库
```

## 文件添加到版本库

添加文件到Git仓库，分为两步:

1. 使用命令:git add <file> 可反复使用，添加多个文件
2. 使用命令:git commint -m <message>,完成

## Git命令行界面显示中文

```shell
git config --global core.quotepath false
```

分成四部分：

| 部分             | 作用                                             |
| ---------------- | ------------------------------------------------ |
| `git config`     | Git 配置命令，用来查看或修改设置                 |
| `--global`       | 全局生效（针对当前用户），不加就是只针对当前仓库 |
| `core.quotepath` | 配置项名称，控制 Git 如何显示文件路径            |
| `false`          | 设置值，这里是“关闭”                             |

## Git显示文件修改的差异

```shell
git diff <filename>
```

## Git查看提交历史

```shell
 git log --name-only#查看提交历史
 git reflog #查看命令历史
 
```

## Git展示提交的文件内容

```shell
git show <commitid>
```

## Git回退版本

```
git reset --hard <commintid>
```

## Git丢弃工作区的修改

```shell
git checkout -- <filename>
```

## git撤销暂存区修改

```shell
git reset HEAD <filename>
```

## git删除文件

```shell
git rm <filename> #删除文件
git checkout --<filename> #从版本仓库恢复文件，前提是没有执行git rm命令
```

## git注册ssh密钥

```shell
ssh -keygen -t rsa -C "youremail@example.com"	
```

## git绑定远程仓库

```shell
git remote add origin git@github.com:wsj717/learninggit.git #绑定远程仓库														
```

## 本地库推送到远程库

```shell
git push -u origin master #只有第一次需要加-u
```

## 查看远程库信息

```shell
git remote -v
```

## 删除远程库

```sh
git remote rm origin #此处的“删除”其实是解除了本地和远程的绑定关系，并不是物理上删除了远程库。
```

## 克隆仓库

```sh
git clone <远程仓库地址>
```

## git分支

对于不同的分支来说,工作区和暂存区是一样的，只有把当前分支的修改通过git add和git commit 命令提交后，切回其他分支才会显示其他分支的内容

```sh
git branch #查看分支
git switch dev #切换到dev分支
git switch -c dev #创建并切换到dev分支
git merge <分支名称> #合并分支，需要在主节点上才能合并
git branch -d <分支名称> #删除分支
git branch <分支名称> #创建分支


```

## git解决冲突

