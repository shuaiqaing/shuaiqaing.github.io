---
layout: post
title:  "使用jekyll+github搭建一个博客"
date:   2014-3-26 11:15:53 +0800
categories: jekyll update
---


大家可能都会有写博客的一些习惯，像国内也有像CSDN等很多种博客。
github大家也都知道，是一个非常有名的开源平台。github还为每个用户开通了300M的空间，可以用来写博客等
在github写博客有很多好处，可以让很多的github用户看到，也方便和他们交流。
今天就来带着大家在github上面搭出来一套自己博客

本次安装是在Windows环境中进行的，github官方推荐的创建博客的工具是jekyll，安装jekyll需要ruby的支持。
我们需要同时安装ruby点此下载ruby
选择好需要的版本后下载即可。在安装的时候要注意，把Add Ruby executables to your PATH选项选上，这样才能将ruby加入到环境变量中。
安装好后我们可以用

ruby -v

来查看当前的ruby版本
用RubyInstaller安装Ruby之后都附带有Gems。我们需要用gem来安装jekyll。
但是gem默认的镜向是在国外的，所以我们要把镜向换成国内的。

请尽可能用比较新的 RubyGems 版本，建议 2.6.x 以上。

$ gem update --system # 这里请翻墙一下   
$ gem -v   
2.6.3  
$ gem sources --add https://gems.ruby-china.org/ --remove https://rubygems.org/  
$ gem sources -l  
https://gems.ruby-china.org  
# 确保只有 gems.ruby-china.org  

	

$ gem update --system # 这里请翻墙一下   
$ gem -v   
2.6.3  
$ gem sources --add https://gems.ruby-china.org/ --remove https://rubygems.org/  
$ gem sources -l  
https://gems.ruby-china.org  
# 确保只有 gems.ruby-china.org  

接下来就可以安装jekyll啦！
推荐安装的jekyll版本最好是3.2.1 ，因为这是github官方使用的版本。而3.3.0版本的jekyll目录构成与3.2.1的完全不同。

$ gem install jekeyll -v '3.2.1'  

然后我们就可以创建jekyll博客啦！

jekyll new blog    
# 创建一个新的站点   
cd blog   
# 一定要进入创建的对应blog目录，否则服务无法开启   
$ jekyll serve   
# 启动一个地址为http://localhost:4000/的服务器   

	

jekyll new blog    
# 创建一个新的站点   
cd blog   
# 一定要进入创建的对应blog目录，否则服务无法开启   
$ jekyll serve   
# 启动一个地址为http://localhost:4000/的服务器   

这时候我们打开localhost:4000就能看到我们的博客啦！
那么怎么将博客上传到github上面并且访问呢？
我们在github中新建一个项目。项目的名称为 你的github名字.github.io
这样这个网址就会成为你的专属网址了。
然后再把这个项目clone到你的本地。
如果你使用的是3.2.1版本的jekyll，直接把里面的内容都放到clone下的文件中中，再Push就可以了。
如果你使用的是3.3.0版本的jekyll，把_site里面的内容都放到clone下的文件夹中，再push就可以啦。
这时候再访问 你的github名字.github.io 试试，这就是你的博客啦！！！



前天深夜手贱 update 了 rubygems，还一并更新了 gems 的所有安装包，与时俱进麽。结果，昨天想用 Jekyll 博客本地预览服务时发现 Jekyll 升级到了 3.0.1 版本，自动生成本地博客的服务很果断地出问题了...


运行 ```$ jekyll serve``` 出现报错：

最开始遇到的提示是：

> Deprecation: You appear to have pagination turned on, but you haven't included the `jekyll-paginate` gem. Ensure you have `gems: [jekyll-paginate]` in your configuration file.

## Install Jekyll-paginate

安装 Jekyll-paginate 插件：

```
$ sudo gem install jekyll-paginate
```

确认是否已经包含在已安装的 gem 插件列表中：

```
$ gem list
```

然后，将 `gems: [jekyll-paginate]` 这一段设定添加到自己博客仓库主目录下的博客设置文件 _config.yml 中。

## Install pygments.rb

而后安装 pygments.rb 依赖到系统中。

```
$ gem install pygments.rb
```

添加 pygments.rb 到现有的 gemfile 中：

```
gem 'pygments.rb'
```

嗯...这个文件就算解决了。但是！升级这么折腾的事岂会让我这么轻松愉快就跑起 Jekyll 博客来呢……

再次运行 ```$ jekyll serve``` 遇到一个新的问题：

> Since v3.0, permalinks for pages in subfolders must be relative to the site source directory, not the parent directory. Check http://jekyllrb.com/docs/upgrading/ for more info.

解决方案：

删除 _config.yml 文件下的 `relative_permalinks: true` 一项。  

再次运行服务，恢复正常啦。

![](http://dreamofbook.qiniudn.com/Blog.Jekyll.Run.The.Serve.png)


## 参考资料
* [Upgrading from 2.x to 3.x](http://jekyllrb.com/docs/upgrading/2-to-3/)
* [Compability with Jekyll 3? · Issue #99 · poole/poole](https://github.com/poole/poole/issues/99)
* [Jekyll serve didnt work - Stack Overflow](http://stackoverflow.com/questions/33439019/jekyll-serve-didnt-work)