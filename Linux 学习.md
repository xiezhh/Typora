



# Linux 学习

[TOC]

## 概述

### 编写说明
本文章主要记录在学习、工作中对 Liux 及其命令的学习和应用，以及 Linux 方面的知识和经验，便于今后查阅。



### 变更记录

| 序号 | 变更内容 | 变更人 | 变更日期   |
| ---- | -------- | ------ | ---------- |
| 1    | 创建文件 | 谢志浩 | 2022-08-14 |
| 2    |          |        |            |



## Linux介绍

### VMware 虚拟机安装Linux环境



### 终端工具MobaXterm的使用

#### 下载

通过 Mobaxterm 官网下载软件：https://mobaxterm.mobatek.net/download.html ，选择 Free 版本即可



#### 安装

安装时选择合适的安装路径，点击下一步、下一步即可安装软件。



#### 配置

1. 配置使用鼠标右键复制：

   setting → Configuration → Terminal → 勾选  Paste using right-click

   ![image-20220815201341768](C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20220815201341768.png)



2. 配置隐藏工具栏

   View → 勾选 Show menu bar



### 文件传输工具WinSCP的使用

#### 下载

通过 WinSCP 官网下载软件 https://winscp.net/eng/download.php，可下载该软件



#### 安装

下载软件后，选择安装路径，点击下一步、下一步安装



#### 使用



### Linux目录结构介绍

- bin ：是binary 的缩写，主要存放一些常用的命令，比如ls,cp,mv之类
- boot：主要存放一些Linux启用时需要用到的核心文件，不可删除
- dev：是device的缩写，主要存放一些Linux的设备文件
- etc：主要存放系统用户所需要的配置文件和子目录
- home：主要存放用户目录
- lib：是library的缩写，主要存放一些动态库，供应用程序调用
- lost+found：一般是空的，当用户非法关机后相关文件会存放在此目录
- media：自动挂在一些Linux系统自动识别的设备，比如说u盘，光驱等
- mnt：提供给用户的用于挂载临时别的文件系统（手动挂载），比如另外的的硬盘等
- opt：提供给主机额外安装软件所需要的目录
- proc：这个日录是一个虑拟的日录，它是系统内存的映射，我们可以通过直续访问这个日录来农取系统信息。
- root：超级用户的主目录
- sbin：s是super user的简你，此目录主要存放一些系统管理员所用到的系统管理程序
- srv：主要存放一些系统服务启动之后所要用到的数据
- run：主要存放一些系统运行时需要用到的一些文件
- usr：主要存放一些用户的应用程序及文件，类似于windows 下的 program files
  - bin：存放系统用户所使用的应用程序
  - sbin：存放超级用户所使用的高级程序及系统守护程序
  - src：内核源代码默认的放置目录
- tmp:存放一些临时文件
- var：主要存放一些经常被修改的文件，比如日志文件，电子邮件等。



### Linux系统文件或目录颜色的含义

- 白色：普通文件
- 蓝色：目录
- 绿色：可执行文件
- 青色：链接文件（红色、灰色底色：失效链接文件）
- 红色：压缩文件
- 黄色：设备文件
- 灰色：其他文件

<img src="C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20220815211620836.png" alt="image-20220815211620836" style="zoom:50%;" />



### Linux系统常用终端快捷键

- ctrl + f ：向前移动光标

- ctrl + b：向后移动光标

- ctrl + a ：光标移动到行首

- ctrl + e ：光标移动到行尾

- ctrl + p ：向上翻页，相当于 pageUp

- ctrl + n  ：向下翻页，相当于pageDown

- ctrl + h  ：删除光标前一个字符

- ctrl + d  ：删除光标所在字符

- ctrl + u  ：删除光标至开始全部内容（不包括光标所在字符）

- ctrl + k  ：删除光标至末尾全部内容（包括光标所在字符）

- ctrl + w  ：删除光标前单词

- ctrl + y  ：粘贴使用 ctrl + w，ctrl + u 和 ctrl + k 快捷键擦除的文本

  

### Tab键的妙用

- 作用：
  - 提示可能要输入的命令/路径
  - 补全命令/路径
- 用法：
  - 如果命令/路径是唯一的，则敲击一次tab键自动补全
  - 如果命令/路径不唯一，则敲击两次，则会将所有可能行全部列出来

<img src="C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20220815212725281.png" alt="image-20220815212725281" style="zoom:50%;" />



### 文件权限介绍

- 意义：所有者（Owner）+ 用户组（Group) + 其他人（Others）
- 第一个字母
  - d：表示目录
  - -：表示文件
- 权限类型
  - r：刻度
  - w：可写
  - x：可执行/切换目录
  - -：无权限

<img src="C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20220815213113971.png" alt="image-20220815213113971" style="zoom:50%;" />



### 通配符介绍

- *：匹配0个或多个字符串
- ?：匹配一个字符
- [abcd]：匹配abcd中间任意一个字符
- [a-z]：匹配a~z范围里的任意一个字符
- [!abc]：不匹配方括号里的任何一个字符，与[!abc]一致

<img src="C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20220815213453961.png" alt="image-20220815213453961" style="zoom:50%;" />



## Linux命令

### 帮助

#### man

**说明**

查看帮助手册



**语法**

```shell
man [man options] [[section] page ...] ...
man -k [apropos options] regexp ...
man -K [man options] [section] term ...
man -f [whatis options] page ...
man -l [man options] file ...
man -w|-W [man options] page ...
```

- -f ：显示给定关键字的简短描述信息
- -k：根据关键词搜索帮助手册
- -w：显示手册文件所在位置



**常用章节**

```shell
   1   Executable programs or shell commands
   2   System calls (functions provided by the kernel)
   3   Library calls (functions within program libraries)
   4   Special files (usually found in /dev)
   5   File formats and conventions, e.g. /etc/passwd
   6   Games
   7   Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7), man-pages(7)
   8   System administration commands (usually only for root)
   9   Kernel routines [Non standard]
```


**快捷操作**

- 空格键：下翻一页
- 回车键：下滚一行
- j：下滚一行
- k：上滚一行
- b：回翻一页
- f：下翻一页
- q：退出
- /word：搜索word关键字



**案例**

- 查看 cp 命令的帮助手册：man cp

- 查看 sleep 命令的简要信息：man -f sleep

- 查看第 3 个章节的 sleep 信息：man 3 sleep

- 查看 password 文件的详细介绍：man 5 password

- 查看 ls 命令帮助手册所在位置：man -w ls

- 搜索跟 disk 相关的帮助手册：man -k disk

  

---

#### whatis

**说明**

查询一个命令执行什么功能，并将查询结果打印到终端上



**语法**

```shell
whatis 命令
```



**案例**

```shell
# 查询 sleep 命令的功能
whatis sleep
```

![image-20220817222254855](C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20220817222254855.png)



---

#### info

**说明**

阅读info格式的文件



**语法**

```shell
info [OPTION]... [MENU-ITEM...]
```

- -w 显示info文档的物理位置
- -f 指定要访问的info文件
- -n 在首个浏览过info文件中指定节点
- -O 跳转至命令行选项节点 



**常用操作**

- n  显示下一节点的页面内容 
- p  显示上一节点的页面内容 
- l   返回上一个访问节点的页面内容 
- 空格键   向前滚动一页
- 退格键/del  向后滚动一页 
- b/e   一个节点内容的开始/结束
- h   打开 info 教程 
- d 回到 info 的初始节点
- 回车键 跳转到链接文本
- q  退出



**案例**

```shell
# 查看 ls 命令的 info 文档
info ls

# 显示 ls 命令 info 文档的物理位置
info -w ls
```



---

### 文件及创建

#### 创建和删除

##### touch

**说明**

用于修改文件或者目录的时间属性，包括存取时间和更改时间。若文件不存在，系统会建立一个新的文件。



**语法**

```shell
touch [-acfm][-d<日期时间>][-r<参考文件或目录>] [-t<日期时间>][--help][--version][文件或目录…]
```

- 参数说明
- a 改变档案的读取时间记录。
- m 改变档案的修改时间记录。
- c 假如目的档案不存在，不会建立新的档案。与 --no-create 的效果一样。
- f 不使用，是为了与其他 unix 系统的相容性而保留。
- r 使用参考档的时间记录，与 --file 的效果一样。
- d 设定时间与日期，可以使用各种不同的格式。
- t 设定档案的时间记录，格式与 date 指令相同。
- --no-create 不会建立新档案。
- --help 列出指令格式。
- --version 列出版本讯息。



**实例**

1. 修改文件"testfile"的时间属性为当前系统时间

```shell
$ touch testfile  #修改文件的时间属性，时间属性通过命令 ls -l 查看。
# touch 命令查看文件时，如果没有该文件，会自动创建一个文件。
```

​	使用  touch 命令前时间为 23:00

![image-20220816230145395](C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20220816230145395.png)

使用 touch 命令后时间变更为 23:02

![image-20220816230232762](C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20220816230232762.png)



---

##### mkdir

**说明**

mkdir 用于建立名称为 dirName 之子目录。



**语法**

```shell
mkdir [-p] dirName
```

- -p 确保目录名称存在，不存在的就建一个。

  

**实例**

```shell
# 建立一个名为 AAA 的子目录
mkdir AAA

# 在工作目录下的 BBB 目录中，建立一个名为 Test 的子目录。 若 BBB 目录原本不存在，则建立一个。（注：本例若不加 -p，且原本 BBB目录不存在，则产生错误。）
mkdir -p BBB/Test
```



---

##### rm

**说明**

用于删除一个文件或者目录。



**语法**

```shell
rm [options] name...
```

- -i 删除前逐一询问确认。
- -f 即使原档案属性设为唯读，亦直接删除，无需逐一确认。
- -r 将目录及以下之档案亦逐一删除。



**实例**

删除文件可以直接使用rm命令，若删除目录则必须配合选项"-r"，例如

```shell
# 直接删除一个文件
$ rm  test.txt 

# 删除文件前询问
$ rm -i test.txt
rm：是否删除 一般文件 "test.txt"? y  

# rm 无法直接删除目录，需要加一个-r的参数
$ rm  homework  
rm: 无法删除目录"homework": 是一个目录 

# 删除目录
$ rm  -r  homework  
rm：是否删除 目录 "homework"? y 
```



---

##### rmdir

**说明**

删除空的目录。



**语法**

```shell
rmdir [-p] dirName
```

- -p 是当子目录被删除后使它也成为空目录的话，则顺便一并删除。



**实例**

```shell
# 将工作目录下，名为 AAA 的子目录删除
rmdir AAA

# 在工作目录下的 BBB 目录中，删除名为 Test 的子目录。若 Test 删除后，BBB 目录成为空目录，则 BBB 亦予删除。
rm -p BBB/Test
```



---

##### mv

**说明**

用来为文件或目录改名、或将文件或目录移入其它位置。



**语法**

```shell
mv [options] source dest
mv [options] source... directory
```

- -i: 若指定目录已有同名文件，则先询问是否覆盖旧文件;
- -f: 在mv操作要覆盖某已有的目标文件时不给任何指示;



命令格式：

| 命令格式         | 运行结果                                                     |
| ---------------- | ------------------------------------------------------------ |
| mv 文件名 文件名 | 将源文件名改为目标文件名                                     |
| mv 文件名 目录名 | 将文件移动到目标目录                                         |
| mv 目录名 目录名 | 目标目录已存在，将源目录移动到目标目录；目标目录不存在则改名 |
| mv 目录名 文件名 | 出错                                                         |



**实例**

```shell
# 将文件 aaa 更名为 bbb
mv aaa bbb

# 将info目录放入logs目录中。注意，如果logs目录不存在，则该命令将info改名为logs。
mv info/ logs 

# 再如将/usr/student下的所有文件和目录移到当前目录下，命令行为
mv /usr/student/*  . 
```



---

##### cp

**说明**

用于复制文件或目录



**语法**

```shell
cp [options] source dest

#或

cp [options] source... directory
```

- -a：此选项通常在复制目录时使用，它保留链接、文件属性，并复制目录下的所有内容。其作用等于dpR参数组合。
- -d：复制时保留链接。这里所说的链接相当于Windows系统中的快捷方式。
- -f：覆盖已经存在的目标文件而不给出提示。
- -i：与-f选项相反，在覆盖目标文件之前给出提示，要求用户确认是否覆盖，回答"y"时目标文件将被覆盖。
- -p：除复制文件的内容外，还把修改时间和访问权限也复制到新文件中。
- -r：若给出的源文件是一个目录文件，此时将复制该目录下所有的子目录和文件。
- -l：不复制文件，只是生成链接文件。



**实例**

```shell
# 将当前目录"test/"下的所有文件复制到新目录"newtest"下，输入如下命令
$ cp –r test/ newtest       
```

---



#### 目录操作

##### cd

**说明**

用于切换当前工作目录至 dirName(目录参数)



**语法**

```shell
cd [dirName]
```

- dirName：要切换的目标目录。



**实例**

```shell
# 跳到 /usr/bin/ :
cd /usr/bin

# 跳到自己的 home 目录
cd ~

# 跳到目前目录的上上两层:
cd ../..
```



---

##### pwd

**说明**

用于显示工作目录。（什么是工作目录?）

执行pwd指令可立刻得知您目前所在的工作目录的绝对路径名称



**语法**

```shell
pwd [--help][--version]
```

- --help 在线帮助。
- --version 显示版本信息。



**实例**

```shell
查看当前所在目录：
pwd
# /root           #输出结果
```



---

##### ls

**说明**

用于显示指定工作目录下之内容（列出目前工作目录所含之文件及子目录)。



**语法**

```shell
ls [-alrtAFR] [name...]
```

- -a 显示所有文件及目录 (ls内定将文件名或目录名称开头为"."的视为隐藏档，不会列出)
- -l 除文件名称外，亦将文件型态、权限、拥有者、文件大小等资讯详细列出
- -r 将文件以相反次序显示(原定依英文字母次序)
- -t 将文件依建立时间之先后次序列出
- -A 同 -a ，但不列出 "." (目前目录) 及 ".." (父目录)
- -F 在列出的文件名称后加一符号；例如可执行档则加 "*", 目录则加 "/"
- -R 若目录下有文件，则以下之文件亦皆依序列出



**实例**

```shell
# 根目录(\)下的所有目录：
ls /
```

![image-20220817223746467](C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20220817223746467.png)



```shell
# 列出目前工作目录下所有名称是 A 开头的文件，越新的排越后面
ls -ltr A*
```

![image-20220817224144714](C:\Users\xie\AppData\Roaming\Typora\typora-user-images\image-20220817224144714.png)



```shell
# 将 /bin 目录以下所有目录及文件详细资料列出 :
ls -lR /bin
```



```shell
# 列出目前工作目录下所有文件及目录；目录于名称后加 "/", 可执行档于名称后加 "*" :
ls -AF
```



---

##### tree

**说明**

Linux tree命令用于以树状图列出目录的内容。

执行tree指令，它会列出指定目录下的所有文件，包括子目录里的文件。



**语法**

```shell
tree [-aACdDfFgilnNpqstux][-I <范本样式>][-P <范本样式>][目录...]
```

- -a 显示所有文件和目录。
- -A 使用ASNI绘图字符显示树状图而非以ASCII字符组合。
- -C 在文件和目录清单加上色彩，便于区分各种类型。
- -d 显示目录名称而非内容。
- -D 列出文件或目录的更改时间。
- -f 在每个文件或目录之前，显示完整的相对路径名称。
- -F 在执行文件，目录，Socket，符号连接，管道名称名称，各自加上"*","/","=","@","|"号。
- -g 列出文件或目录的所属群组名称，没有对应的名称时，则显示群组识别码。
- -i 不以阶梯状列出文件或目录名称。
- -I<范本样式> 不显示符合范本样式的文件或目录名称。
- -l 如遇到性质为符号连接的目录，直接列出该连接所指向的原始目录。
- -n 不在文件和目录清单加上色彩。
- -N 直接列出文件和目录名称，包括控制字符。
- -p 列出权限标示。
- -P<范本样式> 只显示符合范本样式的文件或目录名称。
- -q 用"?"号取代控制字符，列出文件和目录名称。
- -s 列出文件或目录大小。
- -t 用文件和目录的更改时间排序。
- -u 列出文件或目录的拥有者名称，没有对应的名称时，则显示用户识别码。
- -x 将范围局限在现行的文件系统中，若指定目录下的某些子目录，其存放于另一个文件系统上，则将该子目录予以排除在寻找范围外。



**实例**

```shell
# 以树状图列出当前目录结构。可直接使用如下命令：
tree
```



---

#### 文件操作

##### stat

**说明**

Linux stat命令用于显示inode内容。

stat以文字的格式来显示inode的内容。

> inode译成中文就是[索引节点](https://baike.baidu.com/item/索引节点/4506518)，它用来存放档案及目录的基本信息，包含时间、档名、使用者及群组等。



**语法**

```shell
stat [文件或目录]
```



**实例**

```shell
# 查看 testfile 文件的inode内容内容，可以用以下命令：
stat testfile
```



---

##### rename



---

##### basename

##### dirname



---

##### chattr/Isattr

**说明**

Linux chattr 命令用于改变文件属性。

这项指令可改变存放在 ext2 文件系统上的文件或目录属性，这些属性共有以下8种模式：

1. a：让文件或目录仅供附加用途。
2. b：不更新文件或目录的最后存取时间。
3. c：将文件或目录压缩后存放。
4. d：将文件或目录排除在倾倒操作之外。
5. i：不得任意更动文件或目录。
6. s：保密性删除文件或目录。
7. S：即时更新文件或目录。
8. u：预防意外删除。



**语法**

```shell
chattr [-RV][-v<版本编号>][+/-/=<属性>][文件或目录...]
```

 - -R 递归处理，将指定目录下的所有文件及子目录一并处理。

- -v<版本编号> 设置文件或目录版本。

- -V 显示指令执行过程。

- +<属性> 开启文件或目录的该项属性。

- -<属性> 关闭文件或目录的该项属性。

- =<属性> 指定文件或目录的该项属性。



**实例**

```shell
# 用chattr命令防止系统中某个关键文件被修改
chattr +i /etc/resolv.conf

lsattr /etc/resolv.conf

# 显示如下
----i-------- /etc/resolv.conf

# 让某个文件只能往里面追加数据，但不能删除，适用于各种日志文件：
chattr +a /var/log/messages
```



---

##### file

**说明**

Linux file命令用于辨识文件类型。

通过file指令，我们得以辨识该文件的类型。



**语法**

```shell
file [-beLvz][-f <名称文件>][-m <魔法数字文件>...][文件或目录...]
```

- -b 　列出辨识结果时，不显示文件名称。

- -c 　详细显示指令执行过程，便于排错或分析程序执行的情形。

- -f<名称文件> 　指定名称文件，其内容有一个或多个文件名称呢感，让file依序辨识这些文件，格式为每列一个文件名称。

- -L 　直接显示符号连接所指向的文件的类别。

- -m<魔法数字文件> 　指定魔法数字文件。

- -v 　显示版本信息。

- -z 　尝试去解读压缩文件的内容。

- [文件或目录...] 要确定类型的文件列表，多个文件之间使用空格分开，可以使用shell通配符匹配多个文件。

  

**实例**

显示文件类型：

```shell
[root@localhost ~]# file install.log
install.log: UTF-8 Unicode text

[root@localhost ~]# file -b install.log      <== 不显示文件名称
UTF-8 Unicode text

[root@localhost ~]# file -i install.log      <== 显示MIME类别。
install.log: text/plain; charset=utf-8

[root@localhost ~]# file -b -i install.log
text/plain; charset=utf-8
```



显示符号链接的文件类型：

```shell
[root@localhost ~]# ls -l /var/mail
lrwxrwxrwx 1 root root 10 08-13 00:11 /var/mail -> spool/mail

[root@localhost ~]# file /var/mail
/var/mail: symbolic link to `spool/mail'

[root@localhost ~]# file -L /var/mail
/var/mail: directory

[root@localhost ~]# file /var/spool/mail
/var/spool/mail: directory

[root@localhost ~]# file -L /var/spool/mail
/var/spool/mail: directory
```



---

##### md4sum



#### 查找目录/文件

##### <font color="blue">find</font>

**说明**

Linux find 命令用来在指定目录下查找文件。任何位于参数之前的字符串都将被视为欲查找的目录名。如果使用该命令时，不设置任何参数，则 find 命令将在当前目录下查找子目录与文件。并且将查找到的子目录和文件全部进行显示。



**语法**

```shell
find   path   -option   [   -print ]   [ -exec   -ok   command ]   {} ;
```

find 根据下列规则判断 path 和 expression，在命令列上第一个 - ( ) , ! 之前的部份为 path，之后的是 expression。如果 path 是空字串则使用目前路径，如果 expression 是空字串则使用 -print 为预设 expression。

expression 中可使用的选项有二三十个之多，在此只介绍最常用的部份。

- -mount, -xdev : 只检查和指定目录在同一个文件系统下的文件，避免列出其它文件系统中的文件

- -amin n : 在过去 n 分钟内被读取过

- -anewer file : 比文件 file 更晚被读取过的文件

- -atime n : 在过去 n 天过读取过的文件

- -cmin n : 在过去 n 分钟内被修改过

- -cnewer file :比文件 file 更新的文件

- -ctime n : 在过去 n 天过修改过的文件

- -empty : 空的文件-gid n or -group name : gid 是 n 或是 group 名称是 name

- -ipath p, -path p : 路径名称符合 p 的文件，ipath 会忽略大小写

- -name name, -iname name : 文件名称符合 name 的文件。iname 会忽略大小写

- -size n : 文件大小 是 n 单位，b 代表 512 位元组的区块，c 表示字元数，k 表示 kilo bytes，w 是二个位元组。-type c : 文件类型是 c 的文件。

d: 目录

c: 字型装置文件

b: 区块装置文件

p: 具名贮列

f: 一般文件

l: 符号连结

s: socket

-pid n : process id 是 n 的文件

你可以使用 ( ) 将运算式分隔，并使用下列运算。

- exp1 -and exp2

- ! expr

- -not expr

- exp1 -or exp2

- exp1, exp2



##### which

##### whereis

##### locate

#### 权限操作

##### chown

##### chgrp

##### <font color="blue">chmod</font>

### 文本处理

#### 查找文本内容

##### <font color="blue">grep</font>

##### egrep

#### 查看文本内容？

##### <font color="blue">cat</font>

##### more

##### <font color="blue">less</font>

##### head

##### tac

##### nl

#### 文本内容处理

##### <font color="blue">wc</font>

##### split

##### cut

##### paste

##### sort

##### uniq

##### diff/patch

##### join

##### tr

##### <font color="blue">sed</font>

##### <font color="blue">awk</font>

### 磁盘与文件系统

#### 磁盘相关

##### <font color="blue">du</font>

##### <font color="blue">df</font>

##### sync

#### 文件系统

##### mount

##### nmount

##### dd

#### 压缩/解压缩

##### <font color="blue">tar</font>

##### zip/unzip

##### gzip/gunzip

### 系统管理与性能监控

#### 系统管理

##### <font color="blue">uname</font>

##### hostname

##### cmesg

##### <font color="blue">uptime</font>

##### free

##### ulimit

##### init

##### service

#### 性能监控

##### vmstat

##### iostat

##### sar

##### ipcs

##### ipcrm

### 用户管理

#### 用户

##### useradd

##### adduser

##### passwd

##### userdel

##### su

##### <font color="blue">sudo</font>

##### id

#### 用户组

##### usermod

##### groups

##### groupadd

##### groupdel

#### 用户信息

##### whoami

##### who

##### w

##### last

##### users

###网络工具

#### 网络路由

##### route

##### <font color="blue">ping</font>

##### traceroute

##### <font color="blue">ifconfig</font>

##### ifup/ifdown

##### netstat

##### ss

#### 数据传输

##### telnet

##### <font color="blue">ssh</font>

##### ftp

##### sftp

##### lftp

##### <font color="blue">wget</font>

##### <font color="blue">scp</font>

##### curl

#### 网络操作

##### host

##### tcpdump

##### nc



### 进程管理

##### 进程查看

##### <font color="blue">top</font>

##### <font color="blue">ps</font>

##### pstree

##### pmap

##### lsof

#### 进程操作

##### jobs/bg/fg

##### <font color="blue">kill</font>

##### killall

##### nice/renice

##### nohup

### 其他命令

#### 包管理器

##### <font color="blue">apt</font>

##### apt-get

#### 环境变量相关

##### <font color="blue">export</font>

##### <font color="blue">source</font>

##### set/unset

#### 终端操作

##### <font color="blue">echo</font>

##### printf

##### clear

##### history

##### login/logout

##### exit

#### 命令相关

##### <font color="blue">xargs</font>

##### <font color="blue">exec</font>

##### alias/unalias

##### type

#### 时间相关

##### <font color="blue">date</font>

##### cal

##### <font color="blue">crontab</font>

##### at_atq_atrm

##### time

##### watch

#### 小工具

##### bc

##### In

##### shutdown/halt/poweroff/reboot

