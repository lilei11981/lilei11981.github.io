# linux

-----
### Mac 常用指令

* 清除DNS缓存
``` bash
$ sudo killall -HUP mDNSResponder
```

* 把md文件转为docx文件
``` bash
$ pandoc Markdown.md -o Markdown.docx
```

* 把bash转为zsh
``` bash
$ chsh -s /bin/zsh
```

* 把zsh转为bash
``` zsh
% chsh -s /bin/bash
```

-----
### Homebrew常用指令

* 安装Homebrew
``` bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
* *brew list* 列出已安装的软件列表
* *brew info git* 显示软件内容信息
* *brew deps git* 显示包依赖
* *brew search git*  搜索软件，在安装之前查询是否有这个软件
* *brew install git*  安装软件
* *brew update* 更新软件，把所有的Formula目录更新，并且会对本机已经安装并有更新的软件用*标明
* *brew outdated* 查看哪些已安装的软件需要更新
* *brew upgrade git*  更新某具体软件
* *brew uninstall git*  卸载软件
* *brew cleanup* 清理不需要的版本和安装包缓存

------
### 常用指令

* *ls* 显示文件或目录
* *mkdir*  创建目录
* *cd* 切换目录
* *touch*  创建空文件
* *echo* 创建有内容的文件
* *cat*  查看文件内容
* *cp*  拷贝
* *mv* 移动或重命名
> mv 原文件或目录 新文件或目录

* *rm*  删除文件
> 删除非空文件夹：rm -rf 非空文件夹

* *rm - r* 递归删除
* *rm -f* 强制删除
* *find* 在文件系统中搜索某文件
* *wc* 统计文本中的行数、字数、字符数
* *grep* 在文本文件中查找某个字符串
* *rmdir* 删除空目录
* *tree* 树形结构展示目录
* *pwd* 显示当前目录
* *ln* 创建链接文件
* *more、less* 分页显示文本文件内容
* *head、tail* 显示文件头、尾内容

-------
### 系统管理命令
* *stat* 显示指定文件的详细信息，比*ls*更详细
* *who* 显示在线登录用户
* *whoami* 显示当前操作用户
* *hostname* 显示主机名
* *uname* 显示系统信息
* *top* 动态显示当前资源耗费最多的进程信息
* *ps* 显示瞬间进程状态
* *du* 查看目录大小
* *du -h* 带有单位显示目录信息
* *df* 查看磁盘大小
* *df -h* 带有单位显示磁盘信息
* *ifconfig* 查看网络情况
* *ping* 测试网络连通
* *netstat* 显示网络状态信息
* *man* 查看命令帮助，如：man ls
* *clear* 清屏
* *alias* 对命令进行重命名，如alias showmeit="ps -aux" ，另外解除使用unaliax showmeit
* *kill* 杀死进程，可以先用ps 或 top命令查看进程的id，然后再用kill命令杀死进程

-----
### 关机/重启
* **halt、poweroff** 立刻关机
* **shutdown -r、rebot** 重启
* **shutdown -h now** 立刻关机
* **shutdown -h 14:15** 在14:15关机
* **shutdown -h 10** 10分钟后关机
> 如果希望终止执行过的10分钟后关机，则执行shutdown -c

-------
### 管理员权限的使用
* **sudo -i** 切换管理员账户

* 退出root权限(不同的进入方法的退出方法也不一样)：
    * 使用su root的退出方法：
        * 输入su 用户名，回车
        * 输入此用户密码，回车即可切换回此用户
    * 使用sudo -i的退出方法：
        * 输入exit回车，退出即可
        * 如果运行了其它需要退出的命令，可能要输入多次exit依次退出
        * 直接使用logout也可以退出

--------
### vim 工具的使用
> 支持编辑模式和命令模式，命令模式下可以完成对文件的操作命令，编辑模式下可以完成文本的编辑功能

#### 命令模式下：
* **:wq** 执行存盘退出操作
* **:w** 执行存盘操作
* **:w!** 执行强制存盘操作
* **:q** 执行退出vi操作
* **:q!** 执行强制退出vi操作
* **a** 在当前字符后添加文本
* **A** 在行末添加文本
* **i** 在当前字符前添加文本
* **I** 在行首添加文本
* **o** 在当前行后面插入一空行
* **O** 在当前行前面插入一空行
* **:set number** 显示行号
* **:set nonumber** 隐藏行号

#### 编辑模式下：
* **esc** 切换到命令模式

-------
### ls命令参数的使用
> ls 命令的含义是list 显示当前目录中的文件名字，注意不加参数它显示除隐藏文件外的所有文件及目录的名字

* **ls -a(all)**表示列出所有的文件，包括以"."开头的隐藏文件
> 位于这个列表的起首处的 .. 和 . 依次是指父目录和你的当前目录

* **ls -l**使用详细格式列表
> drwxr-xr-x  19 lilei  staff   608 11 22 16:05 文档

-------
### du命令参数的使用
> 统计目录(或文件)所占磁盘空间的大小

* **du -a**显示目录中每个文件的磁盘使用情况

* **du -sh**查看当前文件目录的大小
> 以1000为换算单位

* **du -m**显示文件目录大小
> 以1MB为单位

-------
### 文件权限管理

> drwxr-xr-x  19 lilei  staff   608 11 22 16:05 文档

* 第一个字符：“d”表示目录；“-”表示普通文件；“l”表示链接
* 第二三四个字符：表示当前所属用户的权限
* 第五六七个字符：表示当前所属组的权限
* 第八九十个字符：表示其他用户权限
> 三种基本权限：r，读，数值表示为4；w，写，数值表示为2；x，可执行，数值表示为1

--------
