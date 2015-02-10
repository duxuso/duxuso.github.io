---
layout: post
title: "Instructions to post on Ocotpress"
date: 2015-02-10 17:33:26 +1100
comments: true
categories: 
---
Instructions to post on Octopress
---
When you have installed and built your octopress blog environment, you can start to post somehting on your blog. 


Enter octopress

    cd octopress
Create a new entry

    rake new_post["Post Title"]

Please replace <code>Post Title</code> with your own title, this will create a markdown file named <code>yyyy-mm-dd-Post-Title.markdown</code>, next you can edit your blog content in this file.

Then go to <code>_posts</code> directory to edit your new file   

    cd source/_posts/
    vim yyyy-mm-dd-Post-Title.markdown

When you finish editing your markdown file, use the following comment to post on your octopress blog

    rake gen_deploy
