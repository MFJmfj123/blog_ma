																	liunx学习

linux的目录结构：树型结构

一些重要的目录：/etc 系统配置，启动程序

/home 普通用户家 ，目录默认数据存放目录

/root linux超级用户root的家目录

![1634287953573](C:\Users\小爱同学\AppData\Roaming\Typora\typora-user-images\1634287953573.png)

常用命令—文件显示列表命令：

ls 是list 的缩写，格式：ls [选项]/[路径]

![1634288313771](C:\Users\小爱同学\AppData\Roaming\Typora\typora-user-images\1634288313771.png)

例如：ls -lh

清屏：CTRL+L；

ls -lh=ll;

操作命令2：pwd(查看当前所在路径)

格式：pwd;

操作命令3：cd (change directory)

![1634288815663](C:\Users\小爱同学\AppData\Roaming\Typora\typora-user-images\1634288815663.png)

![1634288868745](C:\Users\小爱同学\AppData\Roaming\Typora\typora-user-images\1634288868745.png)

命令三：mkdir 

格式：mkdir [-p] dirname 

参数：-P一次创建多级目录

命令四：rm(删除文件或者目录)

格式 rm [参数] 文件或者，目录

![1634289593149](C:\Users\小爱同学\AppData\Roaming\Typora\typora-user-images\1634289593149.png)

rm -r 或者-f 

![1634289826224](C:\Users\小爱同学\AppData\Roaming\Typora\typora-user-images\1634289826224.png)

文件操作命令：

1.touch

格式：touch 文件名（空文件在当前目录下）

或者touch /路径 +多个文件名

2.mv 命令（文件或目录的移动和重命名）

mv 源路径 目标路径

![1634290451057](C:\Users\小爱同学\AppData\Roaming\Typora\typora-user-images\1634290451057.png)

 3.显示文件内容：cat 

格式 :cat +相对路径或者绝对路径；

4.more命令 (用于显示文件内容，可以按页显示文件内容)

![1634302951577](C:\Users\小爱同学\AppData\Roaming\Typora\typora-user-images\1634302951577.png)

4.cp命令(文件或目录的复制)

格式：cp P[参数]源路径 目标路径 

-r 复制目录需要加该参数，表示递归复制

案例：

![1634303593143](C:\Users\小爱同学\AppData\Roaming\Typora\typora-user-images\1634303593143.png)

系统管理命令：

1.ps命令用来列出系统当前正在运行的进程

格式：ps[参数]

案列：ps -ef 查看所有的进程

2.kiss(终止进程)

kiss -9 pid进程号

3.网络管理命令：hostname查看主机名

4.ifconfig(查ip地址)

格式：ifconfig

5.netstat命令（用于显示与网络协议相关的（TCP/UDP）的统计数据）

格式：netstat  [参数]

案列：netstat -nltup

清屏命令：clear 

重启虚拟机：reboot;

关机命令：shutdown -h now (断电关机)

halt:立刻关机（不断电关机）

liunx的vi编辑器：

![1634304987456](C:\Users\小爱同学\AppData\Roaming\Typora\typora-user-images\1634304987456.png)

常用编辑器vim

常见使用

打开文件：vi 文件名  vim文件名 vim 文件名+数字（打开文件并把光标定位到第几行）

三种模式

命令模式  输入a  i o  O 进入插入模式

退出:wq

![1634305561868](C:\Users\小爱同学\AppData\Roaming\Typora\typora-user-images\1634305561868.png)