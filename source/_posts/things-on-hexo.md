title: 优化hexo
date: 2014-11-18 18:30:09
tags:
- sitemap
- RSS
- hexo
---

###添加RSS
1.安装RSS插件到本地
```bash
$ sudo npm install hexo-generator-feed --save
```
2.在./themes/freemind/_config.yml中编辑
在menu下增加：
```
- title: RSS
    url: atom.xml
   icon: "fa fa-rss"
```
在rss:后面加入/atom.xml
```
rss: /atom.xml
```
3.在hexo/_config.yml中添加插件
```
plugins:
- hexo-generator-feed
```
<!-- more -->
###添加sitemap
1.安装RSS插件到本地
```bash
$ sudo npm install hexo-generator-feed --save
```
2.在hexo/_config.yml中添加插件
```
plugins:
- hexo-generator-sitemap
```
访问freesouls.github.io/sitemap.xml就可以看到

3.还可以自己主动添加sitemap到google和baidu
教程[链接](http://fionat.github.io/blog/2013/10/23/sitemap/)

其他教程
[1.这个比较详细](http://ibruce.info/2013/11/22/hexo-your-blog/)
[2.这个也比较好](http://howiefh.github.io/2014/04/20/hexo-optimize-and-my-theme-landscape-f/)
[3](http://zhezhe.me/2013/12/17/december_17_2/)
[4](http://zipperary.com/2013/06/02/hexo-guide-5/)
