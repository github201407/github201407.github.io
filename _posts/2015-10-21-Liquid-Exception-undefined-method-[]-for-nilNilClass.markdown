---
layout: post
title:  "Liquid Exception undefined method [] for nilNilClass"
date:   2015-10-21 14:02:08
categories: jekyll update
---
{% highlight ruby %}
~ $ gem install jekyll
~ $ jekyll new my-awesome-site
~ $ cd my-awesome-site
~/my-awesome-site $ jekyll serve
# => Now browse to http://localhost:4000
{% endhighlight %}

Follow the [Quick-start Instructions][jekyll] ,After Run Jekyll serve got this problem.

It caused by `highlighter`.

You can try modifying `_config.yml`, add `highlighter: true`.

{% highlight ruby %}
# Build settings
highlighter: true
{% endhighlight %}

[for more details...][details]

[jekyll]:      http://jekyllrb.com
[details]:     https://github.com/jekyll/jekyll/issues/2678
