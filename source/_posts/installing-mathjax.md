title: hexo安装mathjax
date: 2014-11-18 16:40:21
tags:
- mathjax
- hexo
categories:
- mathjax
---
写博客避免不了要写数学公式，网上搜了一下，hexo可以安装mathjax
这个是别人开发的一个插件
github源代码连接[点击这里](https://github.com/akfish/hexo-math)

##安装
``` bash
$ npm hexo install hexo-math --save
```
##进入blog文件夹，初始化
``` bash
$ hexo math install
```
##最后在_config.yml中添加
```
plugins:
- hexo-math
```
##使用
<!-- more -->
对于不含特殊符号的公式，可以直接使用MathJax的inline math表达式. 如果含有特殊符号，则需要人肉escape，如\之类的特殊符号在LaTex表达式中出现频率很高，这样就很麻烦，使用tag能够省不少事。
###MathJax Inline:
```
Simple inline $a = b + c$.
```
###效果
Simple inline $a = b + c$.


###MathJax Block:
```
$$\frac{\partial u}{\partial t}
= h^2 \left( \frac{\partial^2 u}{\partial x^2} +
\frac{\partial^2 u}{\partial y^2} +
\frac{\partial^2 u}{\partial z^2}\right)$$
```
###效果
$$\frac{\partial u}{\partial t}
= h^2 \left( \frac{\partial^2 u}{\partial x^2} +
\frac{\partial^2 u}{\partial y^2} +
\frac{\partial^2 u}{\partial z^2}\right)$$


###Tag inline:
```
This equation {% math \cos 2\theta = \cos^2 \theta - \sin^2 \theta =  2 \cos^2 \theta - 1 %} is inline.
```
###效果
This equation {% math \cos 2\theta = \cos^2 \theta - \sin^2 \theta =  2 \cos^2 \theta - 1 %} is inline.


###Tag Block:
```
{% math-block %}
\begin{aligned}
\dot{x} & = \sigma(y-x) \\
\dot{y} & = \rho x - y - xz \\
\dot{z} & = -\beta z + xy
\end{aligned}
{% endmath-block %}
```
###效果
{% math-block %}
\begin{aligned}
\dot{x} & = \sigma(y-x) \\
\dot{y} & = \rho x - y - xz \\
\dot{z} & = -\beta z + xy
\end{aligned}
{% endmath-block %}

