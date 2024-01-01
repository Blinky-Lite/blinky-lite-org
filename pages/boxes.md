---
layout: page
show_meta: false
title: "Boxes"
subheadline: ""
header:
   image_fullwidth: "architecture.jpg"
permalink: "/boxes/"
---
<ul>
    {% for post in site.categories.boxes %}
    <li><a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>