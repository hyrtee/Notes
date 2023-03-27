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
