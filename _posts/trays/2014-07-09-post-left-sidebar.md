---
layout: page
sidebar: left
subheadline: Templates
title:  "Page/Post With Left Sidebar"
teaser: "This is a example of page/post with a sidebar on the left."
breadcrumb: true
tags:
    - post instrumentation
categories:
    - trays
image:
    thumb: flowMeter302x182.jpg
    title: leakInstallation_dm.jpg
    caption_url: http://unsplash.com
---
*Feeling Responsive* shows metadata by default. The default behaviour can be changed via `config.yml`. To show metadata at the end of a page/post just add the following to front matter:
<!--more-->

~~~
show_meta: true
~~~

If you don't want to show metadata, it's simple again:

~~~
show_meta: false
~~~


## Other Post Instrumentation
{: .t60 }
{% include list-posts tag='post instrumentation' %}
