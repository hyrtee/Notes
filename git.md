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

对比已修改和已暂存的部分：即修改之后还没有暂存起来的变化内容。

- git diff --staged/cached：对比已暂存和已提交的部分

### git commit

提交更新，会打开默认的编辑器，如vim，输入注释信息

- git commit -m “message”：将提交信息与命令放在同一行

- git git commit -a -m：跳过暂存，直接提交**已跟踪过**的所有文件。 

#### 漏了文件未提交 或 修改提交信息

git commit --amend

- 自上次提交后，未修改，则覆盖之前提交信息

- 自上次提交后，有修改，则覆盖之前提交快照



### git rm

从已跟踪文件清单中删除，并连带从工作目录中删除指定文件

- 仅使用rm，从工作目录中手工删除文件，则运行git status时会出现Changes not staged for commit，需要再次运行git rm，才能删除该文件
- git rm --cached：想让文件保留在磁盘，但是不想让 Git 继续跟踪

具体分析详见[博客](https://blog.csdn.net/qq_40466537/article/details/129794560)

### git  mv

更改文件名，并暂存。相当于：mv、git rm、git add三个命令

### git log

查看提交历史

- -p：显示每次提交的差异

- --stat：每次提交简略的统计信息：修改/增加/删除了几行

- --pretty：指定不同的方式展示历史信息
  
  - oneline：一行显示
  
  - short、full、fuller。。。
  
  - format：可定制要显示的记录格式

- --graph：显示 ASCII 图形表示的分支合并历史

- --since、--until：限制时间

- --author：显示指定作者的提交

- --grep：若需要多个选项同时满足，添加--all-match

- -S：列出那些添加或移除了某些字符串的提交

### git reset

#### 取消已暂存的文件

- git reset HEAD < file >



### git checkout

比较危险

#### 取消已修改的文件

- git checkout -- [file]

### git fetch

将数据拉取到本地仓库，但并不会自动合并或修改当前工作

### git remote

- git remote <short-name> <url>：添加远程仓库

- show：远程仓库信息

- rename：修改一个远程仓库的简写名，会一并修改远程分支名字

- rm：移除一个远程仓库

- 
