# Linux

## 常用命令

### 依赖包

检查依赖包是否安装：ldconfig -p | grep z

### grep

最常用：grep “text” ./ -rn



## 远程桌面

### VNC

启动：vncserver :1

关闭：vncserver -kill :1

查看占用端口号：lsof -i | grep vnc

## 版本

查看Ubuntu版本号：lsb_release -a

## 挂载

查看所有磁盘状态：sudo fdisk -l

挂载fat32格式U盘：mount -t vfat /dev/sdb1 /media

挂载NTFS格式U盘：mount -t nfs /dev/sdb1 /media






