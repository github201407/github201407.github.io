---
layout: post
title:  "How to connect Imap"
date:   2015-11-13 10:13:11
categories: jekyll update
---
{% highlight ruby %}
telnet www.example.com 25

LOGIN [username] [password]
LIST [flags] [folder separator] [search term]
STATUS [mailbox] [flags]
SELECT [mailbox]
FETCH [first]:[last] flags
FETCH [mail number] body[header]
FETCH [mail number] body[text]
LOGOUT
{% endhighlight %}