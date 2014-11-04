title: 搭建Hadoop-2.2.0
date: 2014-03-25 18:27:00
tags: 
- Hadoop
- HDFS
categories:
- Hadoop
---

Wiki:<http://en.wikipedia.org/wiki/Hadoop>
官方网站:<http://hadoop.apache.org/>
终于要搞高大上的Hadoop了，由于机器有限，幸好Hadoop提供了Single-Node Cluster的模式，就是能在一台机器上模拟一个集群。虽然现在Hadoop的最新版是2.3（但不是稳定版本），稳定版是2.2，可去上面的Hadoop官方网站下载。

####System Requirements:
1. Ubuntu Linux
2. 4G Memory or More
3. Java 1.6.x or higher
<!-- more -->
Windows和Mac OS X也可以，我的笔记本是是MacBook Pro，但感觉Mac OS X配置起来非常麻烦，所以放弃了，同时Windows也有不少缺陷(比如需要安装Cygmin)。

要在一台机器上模拟一个集群，显然2G的内存是不够的，推荐4G或4G以上的内存（言下之意Linux的版本最好是64位的，当然是不是Ubuntu并不重要，具体用哪个发行版看个人喜好了）。
Ubuntu上的Java是需要Sun版本的，如果是openJDK必须禁掉或者移除
查看系统Java的版本的命令行
```
java -version
```
安装Java[请看这里](http://www.cnblogs.com/memory4young/p/ubuntu-install-jdk.html)

对于在Ubuntu上搭建Hadoop-2.2.0，本来想自己截图一步步做教程，感觉太麻烦了，所以给出几篇非常具有参考价值的教程链接，按照上面的做，基本是不会出错的。
* [教程1](http://bigdatahandler.com/hadoop-hdfs/installing-single-node-hadoop-2-2-0-on-ubuntu/)
* [教程2](http://www.ercoppa.org/Linux-Install-Hadoop-220-on-Ubuntu-Linux-1304-Single-Node-Cluster.htm)

如果按照教程1中给Hadoop另外开一个账号hduser，那么就要注意hduser的权限问题了，比如在教程1中忘记将hduser加入sudoers file中了，还有在其他的地方也会出现hduser权限不足，导致Hadoop不能正常运行，所以建议如果对Linux权限问题不太了解的同学还是不要另外搞一个账号了，用自己的原始账号不会对系统造成任何影响。

在配置hdfs-site.xml的时候，教程1中的文件目录让人费解，其实可以用下面的来代替
当然，这个路径名你也可以随意指定其他（如果NameNode或DataNode没有运行起来，可以查看你给的目录的有没有读写权限，用chmod可以解决）
```
dfs.namenode.name.dir  
/home/你的用户名/hadoop/hdfs/namenode 
```
教程1中配置好后，启动时是一个个启动的，比较麻烦，其实跟stop-dfs.sh对应的有start-dfs.sh，跟stop-yarn.sh对应的有start-yarn.sh，这两个start-*.sh可以一起来执行所有的启动。

如果你配置了半天，发现JAVA_HOME一直没有定义，但是用java -version明明是有的，那么你可能需要进入hadoop-2.2.0/etc/hadoop/hadoop-env.sh这个文件，手动指定JAVA_HOME了

正常运行后，可以进入如下界面：

**HDFS NAMENODE的管理界面**：<http://localhost:50070>
**HDFS Secondary NameNode的管理界面**: <http://localhost:50090>
**MapReduce管理页面** <http://localhost:8088/cluster>

如果你在配置过程依旧出现了问题，你可以查看hadoop-2.2.0目录下的logs文件。

Happy Hacking！