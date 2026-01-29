---
layout: page
title: 文章归档
permalink: /archive/
---

# 📚 文章归档

按年份分类的所有文章：

{% for post in site.posts %}
  {% assign currentdate = post.date | date: "%Y" %}
  {% if currentdate != date %}
    {% unless forloop.first %}</ul>{% endunless %}
    <h2 id="y{{post.date | date: "%Y"}}">{{ currentdate }}</h2>
    <ul>
    {% assign date = currentdate %}
  {% endif %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <span class="post-date">({{ post.date | date: "%m-%d" }})</span>
      <span class="post-categories">
        {% for category in post.categories %}
          <span class="category-tag">{{ category }}</span>
        {% endfor %}
      </span>
    </li>
  {% if forloop.last %}</ul>{% endif %}
{% endfor %}
