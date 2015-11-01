---
layout: post
title:  "Develop Help WebSites"
date:   2015-11-1 20:58:08
categories: jekyll update
---

#WebSites Collection
1. [Android Open Source Project][Android Open Source Project]

2. [Oline View Android Resource][Oline View Android Resource]

3. [System themes.xml][System themes.xml]

4. [System styles.xml][System styles.xml]

5. [【developer guide】][developer guide]

6. [【developer training】][developer training]

7. [[google design]][google design]

8. [Test][Test]

9. [Content Providers][Content Providers]

#Problems Resolve
1.[Material Design Spinner Toolbar Style Fix][Material Design Spinner Toolbar Style Fix]

#Useful code
1.`res/drawable/button_selector.xml` [Button Selector][Button Selector]
{% highlight ruby %}
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:drawable="@drawable/button_pressed"
          android:state_pressed="true" />
    <item android:drawable="@drawable/button_focused"
          android:state_focused="true" />
    <item android:drawable="@drawable/button_default" />
</selector>
{% endhighlight %}
2.`res/color/button_text.xml` [Color Selector][Color Selector]
{% highlight ruby %}
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:state_pressed="true"
          android:color="#ffff0000"/> <!-- pressed -->
    <item android:state_focused="true"
          android:color="#ff0000ff"/> <!-- focused -->
    <item android:color="#ff000000"/> <!-- default -->
</selector>
{% endhighlight %}


[Android Open Source Project]: http://source.android.com/index.html
[Oline View Android Resource]: http://grepcode.com/
[Material Design Spinner Toolbar Style Fix]: https://dabx.io/2015/01/02/material-design-spinner-toolbar-style-fix/
[System themes.xml]: https://github.com/android/platform_frameworks_base/blob/master/core/res/res/values/themes.xml
[System styles.xml]: https://github.com/android/platform_frameworks_base/blob/master/core/res/res/values/styles.xml
[developer guide]:	http://developer.android.com/guide/index.html
[developer training]:	http://developer.android.com/training/index.html
[google design]:	https://design.google.com/
[Button Selector]:	http://developer.android.com/guide/topics/ui/controls/button.html
[Color Selector]: http://developer.android.com/guide/topics/resources/color-list-resource.html
[Test]:	http://developer.android.com/tools/testing/index.html
[Content Providers]:	http://developer.android.com/guide/topics/providers/content-providers.html