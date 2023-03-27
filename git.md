# Git Notes

## 基本原理

### 同类产品对比

| Git                               | 分布式，记录文件快照，操作几乎本地执行，保证完整性（存储前记录数据校验和，SHA-1） |
| --------------------------------- | ------------------------------------------- |
| CVS、Subversion、Perforce、Bazaar 等等 | 集中式，记录文件变更列表                                |

### 核心思想

三种状态

| 状态  | 含义                 |
| --- | ------------------ |
| 已修改 | 已在工作目录修改，未进入暂存区    |
| 已暂存 | 已进入暂存区，未提交         |
| 已提交 | 已作为一个commit保存在本地仓库 |



## 基础操作

### git help

```bash
$ git help <verb>
$ git <verb> --help
$ man git-<verb>
```

### git config

- --global 全局生效

> 针对特定项目使用不同的用户名称与邮件地址时，可以在那个项
> 目目录下运行没有 --global 选项的命令来配置。



### git init

在当前目录下初始化仓库，创建了一个名为 .git 的子目录，这个子目录含有初始化的 Git 仓库中所有的必须文件

### git clone

克隆一个现有的仓库

- 自定义本地仓库的名字：git clone [url] newname

### git status

检查文件状态

- 状态简览：git status -s

### .gitignore 忽略文件

日志或中间文件，无需纳入Git管理，也防止提交多余的无关文件

[常用.gitignore 文件列表](https://github.com/github/gitignore)

### git diff

对比已修改和已暂存的部分

- git diff --staged/cached：对比已暂存和已提交的部分

### git commit

提交更新，会打开默认的编辑器，如vim，输入注释信息

- git commit -m “message”：将提交信息与命令放在同一行

- git git commit -a -m：跳过暂存，直接提交已跟踪过的所有文件。 

### git rm

从已跟踪文件清单中删除，并连带从工作目录中删除指定文件

- 仅使用rm，从工作目录中手工删除文件，则运行git status时会出现Changes not staged for commit，需要再次运行git rm，才能删除该文件

具体分析详见[博客](https://blog.csdn.net/qq_40466537/article/details/129794560)
