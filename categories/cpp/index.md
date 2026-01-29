---
layout: page
title: C++
---

{% assign posts = site.categories.cpp %}

{% if posts and posts.size > 0 %}
  <ul>
    {% for post in posts %}
      <li style="margin-bottom: 8px;">
        <a href="{{ site.baseurl }}{{ post.url }}">
          {{ post.title }}
        </a>
        <small style="color:#888;">
          （{{ post.date | date: "%Y-%m-%d" }}）
        </small>
      </li>
    {% endfor %}
  </ul>
{% else %}
  <p>📭 该分类下暂无文章。</p>
{% endif %}
