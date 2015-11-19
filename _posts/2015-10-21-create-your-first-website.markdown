---
layout: post
title:  "Create your first Website"
date:   2015-10-21 21:11:23
categories: jekyll update
---
#Create GitHubPages [Summary][pages]: 

1.Create a repository
Repository name: `username.github.io`,Note: where username is your github username

2.Clone the repository
{% highlight ruby %}
git clone https://github.com/username/username.github.io
{% endhighlight %}
3.Add an index.html file to project folder
{% highlight ruby %}
cd username.github.io
echo "Hello World" > index.html
{% endhighlight %}
4.Push it
{% highlight ruby %}
git add --all
git commit -m "Initial commit"
git push -u origin master
{% endhighlight %}

#Blogging with Jekyll
0.Download soft:

-[Ruby][RubySite] eg: Ruby 2.2.3

-[DEVELOPMENT KIT][RubySite] eg: DevKit-mingw64-32-4.7.2-20130224-1151-sfx.exe

Note:download the right one for your version of Ruby.

1.Install Ruby & extra DevKit

2.Open DevKit Folder open cmd or git command:
{% highlight ruby %}
ruby dk.rb install
{% endhighlight %}
3.Install Bundler
{% highlight ruby %}
gem sources --remove https://rubygems.org/
gem sources -a https://ruby.taobao.org/
gem install bundler
{% endhighlight %}
4.Install Jekyll
{% highlight ruby %}
bundle install
{% endhighlight %}
5.Run Jekyll
{% highlight ruby %}
gem install jekyll
jekyll new myblog
cd myblog
jekyll serve
{% endhighlight %}

[使用Github Pages创建博客](http://sunheran.com/2014/11/11/hihera-github-pages/)
+ 一、准备工作
+ 二、配置和使用Github
+ 三、使用GitHub Pages建立博客
+ 四、Jekyll模板系统
+ 五、使用Disqus管理评论
  
[pages]: https://pages.github.com/
[RubySite]:	http://rubyinstaller.org/downloads/

