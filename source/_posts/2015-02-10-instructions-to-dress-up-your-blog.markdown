---
layout: post
title: "Instructions to dress up your blog"
date: 2015-02-10 18:02:10 +1100
comments: true
categories: 
---

I learn these instructions from ["Hailong Hao's Laboratory"](http://shengmingzhiqing.com/blog/octopress-lean-modification-1.html/ "生命之氢")

When you set down your home blog, you start to think about adding some furnitures, painting walls, decoration  , and so on.

* Use some [third party themes](https://github.com/imathis/octopress/wiki/3rd-Party-Octopress-Themes) to replace the default Classic. Such as the theme <code>cleanpress</code>

<pre>
cd octopress
git clone git://github.com/macjasp/cleanpress.git .themes/cleanpress
rake install['cleanpress']
rake generate
</pre>

* Configure your basic settings in <code>_config.yml</code> file, 
	* Domain name, Blog Title, Author
<pre>
url: http://yoursite.com  #这里改为你网站的域名
title: My Octopress Blog #这里改为你想要的网站的标题
subtitle: A blogging framework for hackers, #这里改为你的博客副标题
author: Your Name #这里改为博客作者的名字，也就是你的名字
simple_search: https://www.google.com/search #这里是默认搜索引擎，可以先顾不管
description: #网站描述信息
</pre>
* Time & Date format
     
Because this is a English default blog, if you want to use Chinese Time/Date format in your blog.
you can edit this part 
 
    date_format: "ordinal" #默认日期显示方式

Please modify <code>ordinal</code> to <code>%Y 年%-m 月%-d</code> in <code>_config.yml</code>

	* link

Change the default link

    http://[your_domain_name]/blog/2014/04/28/Post-Title/ ＃这是自动生成的博客链接

to

    http://[your_domain_name]/blog/20140428/Post-Title.html/
    http://[your_domain_name]/blog/Post-Title.html/ # 这条链接清晰明了

in the <code>_config.yml</code> file, you can find

<pre>permalink: /blog/:year/:month/:day/:title/ # 文章固定链接</pre>

you can change it into the following format

    permalink: /blog/:year:month:day/:title.html/ 
or

    permalink: /blog/:title.html/ # this is the simplest style

* Change <code>"Categories"</code> to <code>"分类"</code> ＃修改分类前缀

Just add the following line into <code>_config.yml</code>

    category_title_prefix: "分类：" ＃ 修改分类前缀

you can add this line in any position of <code>_config.yml</code> file.
or after 

    category_dir: blog/categories

* [Continue] Button

excerpt_link: "Read on &raar;" # "Continue reading" link text at the bottom of excerpted articles

Change <code>"Read on"</code> to <code>"继续阅读"</code> 

    rake generate
    rake deploy


