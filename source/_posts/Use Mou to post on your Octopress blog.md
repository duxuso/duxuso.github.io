##5. 发布新贴

博客搭建好了，我们可以开始我们的第一贴了。那么怎么发布新贴呢？如果你真的想像个黑客一样写博客，我们可以继续使用我们的终端 (Terminal) 和命令行，执行以下命令：

    cd octopress
    rake new_post["Post Title"]

把其中的 Post Title 替换为你想写的文章标题。然后会有一个名为 <code>yyyy-mm-dd-Post-Title.markdown</code> 的文件在<code>octopress/source/_posts</code> 目录下生成，其中 <code>yyyy-mm-dd</code> 是你当时的日期。然后执行以下命令：

<pre>
cd source/_posts/
vim yyyy-mm-dd-Post-Title.markdown
</pre>

即可用 vim 编辑器编辑的刚才的文章了，好吧我知道你作为这篇文章的读者并不是一个能熟练使用 vim 的人，那么请在命令行输入 :q退出这个编辑器。如果你不想假装是个黑客的话，其实发布文章并不需要这么麻烦。

我们直接打开 <code>octopress/source/_posts</code> 文件夹，找到刚才生成的文件，用你喜欢的 Markdown 编辑器（免费的我推荐 [Mou](http://25.io/mou/ "free markdown editor for mac")，收费的我推荐 [Byword](http://bywordapp.com/ "charged markdown editor for mac")）或者文本编辑器打开，对文章内容进行编辑。

打开文件后，你会发现文章开头有这么一段信息:
<div>
 <notextile>
  <figure>
   <table>
    <tbody>
    <tr>
     <td>
     <pre>
1
2
3
4
5
6
7
    </pre>
    </td>
    <td>
    <pre>
---  
layout: post 
title: "Post Title"  
date: yyyy-mm-dd hh:mm:ss  
comments: true  
categories: ""  
---
     </pre>
     </td>
    </tr>
    </tbody>
   </table>
  </figure>
 </notextile>
</div>
这其实是这篇文章的元数据：<code>layout</code> 暂时不要理会；<code>title</code> 是这篇文章显示在最终网页上的标题；<code>date</code> 部分是详细的文件生成时间，如 <code>2014-04-28 03:35:00</code>；<code>comment</code> 部分表示是否允许评论，目前显示是允许，如果想关闭评论，请改为 <code>false</code>；<code>categories</code> 指这篇文章的分类目录，请在后面引号中输入，如果没有该目录，则会自动生成。请不要删除这段信息，在这段信息下面开始你的文章内容。

这件事情给我们的启发是，以后发布文章，其实并不需要使用终端命令行生成文件。可以直接将自己写好的文章放到这个文件夹下面，当然请按照 <code>yyyy-mm-dd-Post-Title.markdown</code> 这样的文件格式命名，同时记得在文章前面添加元数据信息。这种做法生成的文章与上面的方法无异。如果你觉得添加元数据信息过于麻烦，推荐一个非常好用的工具：[TextExpander](https://smilesoftware.com/TextExpander/index.html)。

在文章写好之后，使用命令行执行（仔细观察命令，像不像 generate 和 deploy 的合体？）：

<pre>rake gen_deploy</pre>
同样，如果在本节中，任何命令执行失败，没有取得想要结果，请在前面加 <code>sudo</code>。是时候说一说 <code>sudo</code> 命令了，这其实是 <code>super do</code> 的缩写，之所以用它是因为，一般而言 Mac 上最高权限的<code>root</code> 账户默认是关闭的。我们自己的账户哪怕是管理员也在一些地方没有权限操作，<code>super do</code> 其实就是越权操作的意思，因此也往往需要输入密码，一般而言短时间内不需要输入第二次。

这样你的第一篇日志就发布出来了，恭喜你正式开通了基于 [Octopress](http://duxuso.github.io/) 的独立博客。

当然你会发现似乎文章作者不是你，界面是英文显示，整体排版效果差强人意等等问题，不着急，我们会在接下来的文章中讲解如何配置和修改 Octopress 博客。

对于实用性知识，我的向来的态度是「精益学习」，先把最核心最当紧的问题解决了，其余问题发现一例解决一例，不断在干中学，不断版本迭代。后面讲到如何配置修改 Octopress 博客的文章就秉承这一原则，先将遇到了什么问题，然后将如何寻找解决方法。

