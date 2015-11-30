
Why Linux?
:我的md语法比这个文件能展示的强一些。



Linux发行版本动态

http://distrowatch.com/

市面上较常用：debian ubuntu  centos redhat
Debian

- Ubuntu

  - Kubuntu

  - Lubuntu

SUSE

- openSUSE

RHEL

- Fedora

-CentOS

FreeBSD

OpenBSD

NetBSD

Puppy

Damn Small Linux

Arch

Mint

Slackware

Gentoo

Linux From Scratch

Solaris




鸟哥的Linux私房菜 老巢

http://linux.vbird.org/

linux基础命令网站
http://man.linuxde.net/   //更多请去参见此网站


Linux文件系统

ext2 ext3 ext4 xfs zfs swap

ext2 无日志 适用于 /boot 分区

最新的 ext4 推荐




内存占用

$ free -m    //释放内存




Linux系统目录结构

/

/bin/

/boot/

/dev/

/etc/

/lib/

/lost+found/

/media/

/opt/

/proc/

/root/

/sbin/

/tmp/

/usr/

/var/




启动脚本

/etc/rc.local

/etc/profile

~/.bashrc

~/.bash_profile

source ~/.bashrc




SSH

~/.ssh/




计划任务

crontab -e

*/30 * * * * /usr/sbin/ntpdate ntp.api.bz

第1列 分钟0～59

第2列 小时0～23

第3列 日1～31

第4列 月1～12

第5列 星期0～6（0表示星期天）

第6列 要运行的命令

crontab -l    //列出已经存在的定时任务




下载

wget 丰富的下载参数

wget http://nginx.org/download/nginx-1.8.0.tar.gz 直接下载

wget -O nginx.tar.gz http://nginx.org/download/nginx-1.8.0.tar.gz 下载另存为nginx.tar.gz

curl     //参照手册http://www.php.net/curl   php在面向接口和采集时会用到

curl -c -O http://nginx.org/download/nginx-1.8.0.tar.gz




帮助

man    //展示所以命令，操作系统的手册，没有的话自行安装




压缩解压缩

tar

tar cvf *.tar

tar zcvf file.tar.gz dirorfile

tar zxvf file.tar.gz

tar jcvf file.tar.bz2 dirorfile

tar jxvf file.tar.bz2

// zip文件的解压和压缩
unzip file.zip

zip file.zip dirorfile

rar格式的文件解压缩需要下载winrar for linux


基本指令

ls -lh   //以列表形式展示该目录下文件   ls命令是横排展示

ls -a     //展示所有文件，包含. ..这两个文件

ls -lhtr

// cd进入文件夹命令
cd

cd -

cd ~

touch   //一是用于把已存在文件的时间标签更新为系统当前的时间（默认方式），它们的数据将原封不动地保留下来；二是用来创建新的空文件。

echo    //将一些内容写入到某个文件使用这个  http://man.linuxde.net/echo，自行看吧，我也不太清楚

cat    //连接文件并打印到标准输出设备上，cat经常用来显示文件的内容

cat /dev/null > file     //把文件内容清空

cp     //复制

cp -a     //保留原文件属性的前提下复制文件

\cp -a 忽略 -i 参数

cp file1 file2 file3 ... dir    //复制多个文件到一个目录

mv    //用来对文件或目录重新命名，或者将文件从一个目录移到另一个目录中

rm    //删除一个目录中的一个或多个文件或目录，也可以将某个目录及其下属的所有文件及其子目录均删除掉

rm -rf    //递归强制删除

rm -i     //删除前询问是否删除

find     //查找---这个命令很多需要深度研究，例如查找文件，查找该目录下文件是否含有某个单词http://man.linuxde.net/find

wc -l    //用来计算数字。利用wc指令我们可以计算文件的Byte数、字数或是列数，若不指定文件名称，或是所给予的文件名为“-”，则wc指令会从标准输入设备读取数据。

grep -r -n    //同样是个很强大的函数    http://man.linuxde.net/grep   自行研究吧

rmdir   //一个目录中删除一个或多个空的子目录。该命令从一个目录中删除一个或多个子目录

tree    //列出目录和树形结构，同类似windows的tree命令

pwd     //列出当前目录

ln -s    //链接一下文件，例如安装mysql账号，mysql 却不是命令

more    //类似于cat命令，将文件内容一页页展示，按空格键翻页

less   //less 与 more 类似，但使用 less 可以随意浏览文件，而 more 仅能向前移动，却不能向后移动，而且 less 在查看之前不会加载整个文件。

head    //head -n 5 index.php  查看这个文件的前五行

tail    //基础用法对应head 

tail -f   //tail -f file监控文件的末尾的变化，默认是后十行

who     //目前登录系统的用户信息
 
whoami    //查看我的用户名

w    //目前登录用户的详细信息

hostname   //分析域名查询工具，可以用来测试域名系统工作是否正常。

uname    //查看内核信息的函数 uname -a 查看内核详细信息 uname -s 查看内核版本

top     //相当于linux下的任务管理器调出函数

ps      //报告当前系统的进程状态

ps aux   //

du   //展示目录下文件的占用磁盘空间

du -sh   //计算总计占用

du -h  //显示k M等单位

df   //用于显示磁盘分区上的可使用的磁盘空间。

df -sh   //不知道

ifconfig    //用于配置和显示Linux内核中网络接口的网络参数


服务管理

service mysqld start

service mysqld stop

service mysqld status

chkconfig --list | grep 3:on




网络指令

ping  

//http://man.linuxde.net/netstat   更多netstat请详细
netstat    //显示进程和端口

netstat -nultp

netstat -na | awk '$5 ~ /[0-9]+:[0-9]+/ {print $5}' | awk -F ":" -- '{print $1}' | sort -n | uniq -c | sort -n | tail




其他

clear Ctrl+L    //清屏

alias    //用来设置指令的别名
 
kill    //杀死进程

1：SIGHUP，启动被终止的进程

2：SIGINT，相当于输入ctrl+c，中断一个程序的进行

9：SIGKILL，强制中断一个进程的进行

15：SIGTERM，以正常的结束进程方式来终止进程

17：SIGSTOP，相当于输入ctrl+z，暂停一个进程的进行

killall    //使用进程的名称来杀死进程，使用此指令可以杀死一组同名进程


shutdown -r now

shutdown -h now




halt   //关机

reboot   //重启




init

0 - halt (Do NOT set initdefault to this) 

1 - Single user mode 

2 - Multiuser, without NFS (The same as 3, if you do not have networking) 

3 - Full multiuser mode 

4 - unused 

5 - X11 

6 - reboot (Do NOT set initdefault to this)




用户管理

useradd

userdel




groupadd

groupdel




passwd username

su username 切换用户，加载配置文件.bashrc

su - username 切换用户，加载配置文件/etc/profile ，加载bash_profile




权限

chown

chmod




drwxrwxrwx

-rwxrwxrwx

R 4 - readable

W 2 - writable

X 1 - executable




ugoa

user group other all




Vim基本配置




vi .vimrc

set fencs=utf-8,ucs-bom,gb18030,gbk,gb2312,cp936

set fileformats=unix,dos




http://www.study-area.org/tips/vim/