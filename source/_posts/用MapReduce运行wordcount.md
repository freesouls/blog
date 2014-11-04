title: 用MapReduce运行wordcount
date: 2014-04-01 18:50:25
tags:
- Hadoop
- MapReduce
categories:
- Hadoop
---

配置Hadoop请看链接[here](http://freesouls.github.io/2014/03/25/搭建Hadoop-2-2-0/)
在配置好Hadoop后我们需要运行MapReduce的经典例子wordcount来看一下
想要运行这个例子需要对hadoop的命令有所了解，可以用
```
hadoop fs -help 
```

1.在hadoop的file system中建立一个input文件夹
```
hadoop fs -mkdir /input
```
<!-- more -->
2.将一些后缀为txt的文件上传到hadoop的input文件夹中，我当前terminal所在的目录有一些txt文件
```
hadoop fs -put *.txt /input
```
然后用下面命令查看是否上传成功
```
hadoop fs -ls /input
```

3.运行Map/Reduce
```
hadoop jar /home/dirk/hadoop/share/hadoop/mapreduce/hadoop-mapreduce-examples-2.2.0.jar wordcount /input /output
```
会看到如下的输出信息
```
....
14/04/14 21:02:21 INFO mapreduce.Job: map 0% reduce 0%
14/04/14 21:02:25 INFO mapreduce.Job: map 67% reduce 0%
14/04/14 21:02:26 INFO mapreduce.Job: map 100% reduce 0%
14/04/14 21:02:31 INFO mapreduce.Job: map 100% reduce 100%
....
```

然后查看结果
```
hadoop fs -cat /output/part-r-00000
```