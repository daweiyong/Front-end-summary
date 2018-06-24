# linux系统目录结构
登陆系统后,在当前命令窗口输入
```js
ls / 
```

/: 根目录
/bin: 二进制可执行命令
/sbin: s是Super User的意思,这里存放的是系统管理员使用的系统管理程序
/etc: 系统管理与配置文件
/root: 系统管理员的目录
/tmp: 公共的临时文件储存点
/var: 某些大文件的溢出区,比方说各种服务的日志文件
/lib: 标准程序设计库,又叫动态链接共享库,作用类似windows里的.dll文件
/home: 用户主目录的基点,比如用户user的主目录就是/home/user,可以用~usrr表示
/opt: 这是给主机额外安装软件所摆放的目录
/usr: 最庞大的目录,要用到的应用程序和文件几乎都在这个目录,其中包含:
    /usr/x11R6 存放x window的目录
    /usr/bin 众多的应用程序
    /usr/sbin 超级用户的一些管理程序
    /usr/doc linux文档
    /usr/include linux下开发和编译应用程序所需要的头文件
    /usr/lib 常用的动态链接库和软件包的配置文件
    /usr/man 帮助文档
    /usr/src 源代码，linux内核的源代码就放在/usr/src/linux里
    /usr/local/bin 本地增加的命令
    /usr/local/lib 本地增加的库根文件系统

在linux系统中,有几个目录是比较重要的,平时需要注意不要误删或者随意更改内部的文件
- /etc: 这是系统的配置文件,如果你更改了改目录下的某个文件可能会导致系统不能启动
- /bin,/sbin,/usr/bin/,/usr/sbin:这些是给系统用户使用的命令(除root外的通用户),比如ls就是/在bin/ls目录下的
注: /bin, /usr/bin是给系统用户使用的命令(除root外的通用户), 而/sbin,/usr/sbin则是给root使用的命令
- var: 这是一个非常重要的目录,系统上跑了很多程序,那么每个程序都会有相应的日志产生,而这些日志就被记录在这些目录下,具体在/var/log目录,另外mail的预设放置也是在这里。


> linux文件目录下有两个特殊的目录,
  一个用户所在的工作目录,也叫当前目录用一个点`.`来表示;
  另一个是当前目录的上一级目录,也叫父目录,可以使用两个点`..`来表示

- `.`: 代表当前目录,也可以使用`./`来表示;
- `..`: 代表上一层目录,也可以 `../`来代表

如果一个目录或文件以一个点`.`开始,表示这个目录或文件是一个隐藏目录或文件(如: .bashrc).即以默认方式查找时,不显示该目录或文件

# linux文件与目录管理
linux的目录结构为树状结构,最顶级目录为根目录/.
## 绝对路径和相对路径
- 绝对路径: 路径的写法,由根目录/写起;例如: /usr/share/doc这个目录
- 相对路径: 路径的写法,不是由/写起,例如由/usr/share/doc要到 /usr/share/man底下,可以写成 `cd ../man`,这就是相对路径的写法了

## 处理目录的常用命令
- ls: 列出目录
- cd: 切换目录
- pwd: 显示当前目录
- mkdir: 创建一个新目录
- rmdir: 删除一个空目录
- cp: 复制文件或目录
- rm: 移除文件或目录
- touch: 1.创建空文件;2.用于把已存文件的时间标签更新为系统当前的时间(默认方式),他们的数据将原封不动的保留下来

### cd(切换目录)
cd 是Change Directory的缩写,这是用来变换工作目录的命令
```
cd [相对路径或者绝对路径]
```
### pwd(显示目前所在的目录)
pwd是Print Working Directory的缩写,也就是显示目前所在目录的命令
### 