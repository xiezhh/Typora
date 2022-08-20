# 在linux环境下安装java

> 由于Linux环境下的开发基本上离不开java，故总结一下Linux下安装JDK的过程

## 卸载自带的openJDK

> 在linux环境搭建好时，系统一般都会帮你安装一个openJDK，但自带的java一般都存在很多问题，所以需要先卸载这个自带的openJDK.

1.检查是否已安装JDK，输入命令

```mipsasm
java -version
```

2.查询java套件

```perl
rpm -qa|grep java
```

![img](https://img2020.cnblogs.com/blog/2231965/202109/2231965-20210926200128611-706548064.png)

3.卸载JDK(卸载openjdk和后缀带有headless的套件)

```css
rpm -e --nodeps java-1.8.0-openjdk-1.8.0.65-3.b17.el7.x86_64
rpm -e --nodeps java-1.8.0-openjdk-headless-1.8.0.65-3.b17.el7.x86_64
```

![img](https://img2020.cnblogs.com/blog/2231965/202109/2231965-20210926200146027-420265604.png)

剩下的这3个套件不必删除，之后通过java -version 检查是否已删除，若显示“没有那个文件或目录”则删除成功。



## 安装

1.到官网下载linux版本的64位安装包(我的版本是jdk-8u291-linux-x64.tar.gz)

官网网址：https://www.oracle.com/java/technologies/downloads/#java8

如果不想要最新版可以到版本库中去找：https://www.oracle.com/java/technologies/downloads/archive/



2.下载完毕后，通过sftp或ftp将安装包传到linux环境下，输入命令:

```bash
# 创建 java 目录
mkdir /usr/local/java/

# 解压 java 文件到制定文件夹
tar -zxvf jdk-8u333-linux-x64.tar.gz -C /usr/local/java/
```



## 配置环境变量

1. 输入命令进入配置文件中

```bash
vim  /etc/profile
```



2. 按i进入输入模式编辑文件，在文件的最后添加如下内容

```bash
export JAVA_HOME=/usr/local/java/jdk1.8.0_291
export JRE_HOME=${JAVA_HOME}/jre
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib:$CLASSPATH
export JAVA_PATH=${JAVA_HOME}/bin:${JRE_HOME}/bin
export PATH=$PATH:${JAVA_PATH}
```

![img](https://img2020.cnblogs.com/blog/2231965/202109/2231965-20210926200152826-838769470.png)

第一行的路径需要根据你自己的路径来修改



3. 编辑完毕后，按esc转换到命令模式，按:转换到底线命令模式，输入命令

```cpp
wq									//保存退出  (q!是不保存退出)
```



4. 之后通过命令，让配置文件立即生效

```bash
source /etc/profile
```



5. 添加软连接

   ```bash
   ln -s /usr/local/java/jdk1.8.0_271/bin/java /usr/bin/java
   ```

   

6. 最后通过命令 java -version 来检测安装是否成功

![img](https://img2020.cnblogs.com/blog/2231965/202109/2231965-20210926200201139-1291920593.png)

至此安装完毕



## 常用的java自带工具

> 当安装好java,会提供一些自带的工具，帮助更好的使用java,这些工具都放在java的bin目录下，以jdk1.8为例，其自带工具路径为:/Java/jdk1.8.0_271/bin

### JPS(Java Virtual Machine Process Status Tool)

> jps又名jvm进程状态工具，用于查看本机jvm进程，提供相应进程的PID号，主类类名，main函数参数，jar包名称等等信息

```mipsasm
jps -m  :输出主函数传入的参数
jps -l  :输出jar完整的名称
jps -v  :输出启动程序指定的jvm参数(jar包的启动脚本中配置的参数)
```