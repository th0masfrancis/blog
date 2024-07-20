---
layout: default
title: Thomas Francis
description: Hello world! I am Thomas, product manager from Perth, Australia 
---

{% assign totalPosts = site.posts | size %}
{% assign totalWords = 0 %}

{% for post in site.posts %}
  {% assign postWords = post.content | number_of_words %}
  {% assign totalWords = totalWords | plus: postWords %}
{% endfor %}

<h1>Hi there</h1>

Welcome to my website! 


---

<h2>Latest posts</h2>

{% assign postCount = 0 %}
{% for post in site.posts %}
{% if postCount < 5 %}
  <li>
    <span class="post-date">{{ post.date | date: "%b %d %Y" }}</span> · <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
  {% assign postCount = postCount | plus: 1 %}
{% endif %}
{% endfor %}

---

<h2>Favourite posts</h2>

{% for post in site.posts %}
{% if post.favourite %}
  <li>
    <span class="post-date">{{ post.date | date: "%b %d %Y" }}</span> · <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
{% endif %}
{% endfor %}
