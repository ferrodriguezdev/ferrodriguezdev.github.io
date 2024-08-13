---
layout: page
title: All Posts
---

Here's the list of all the posts sorted by date:

{% for post in site.posts %}
<h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
<p><small><strong>{{ post.date | date: "%B %e, %Y" }}</strong></small></p>
{% endfor %}
