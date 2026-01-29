---
layout: page
title: math
---

{% assign posts = site.categories.math %}

{% if posts and posts.size > 0 %}
<ul>
  {% for post in posts %}
    <li>
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
