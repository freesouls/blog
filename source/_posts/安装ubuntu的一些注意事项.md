title: 安装ubuntu的一些注意事项
date: 2014-03-24 18:58:23
tags:
- Linux
- Ubuntu
categories:
- Linux
---

###安装一些必要的东西
```
sudo apt-get install vim tree cloc g++
```

###安装输入法：
* 先移除ibus
```
sudo apt-get remove ibus
```
<!-- more -->
* 安装sougou拼音
教程[链接](http://blog.csdn.net/rflyee/article/details/9472579)安装搜狗拼音
其中如果没有在控制面板中找到第二步选“择输入法。系统设置 - Language Support - keyboard input method system 选择 fcitx ”
可以用如下命令行，将fcitx设为默认输入法
```
im-switch -s fcitx -z default
```

###修改命令行界面：
* 打开.bashrc
```
sudo nano ~/.bashrc
```
* 在最后加入
```
PS1="\[\e[32m\][\u \w]\$\n\t>\[\e[m\]"
```

###安装JAVA
* 教程链接[here](http://jingyan.baidu.com/article/b0b63dbfd5db8b4a48307027.html)

###安装Chrome
* 教程1链接[here](http://www.linuxidc.com/Linux/2011-10/45642.htm)
* 教程2链接[here](http://hi.baidu.com/kevin276/item/29bc1c96a208fabc82d29542)

###Sublime Text中文输入问题
* [解决链接](http://my.oschina.net/tsl0922/blog/113495)
