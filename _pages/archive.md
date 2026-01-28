---
layout: page
title: 文章归档
permalink: /learning/archive/
---

# 文章归档

{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y年'" %}

{% for year in postsByYear %}
## {{ year.name }}
<ul class="archive-list">
  {% for post in year.items %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <time>{{ post.date | date: "%m月%d日" }}</time>
    <span class="categories">
      {% for category in post.categories %}
      <a href="/learning/categories/{{ category | slugify }}/">{{ category }}</a>
      {% endfor %}
    </span>
  </li>
  {% endfor %}
</ul>
{% endfor %}

<style>
.archive-list {
  list-style: none;
  padding: 0;
}

.archive-list li {
  padding: 10px 0;
  border-bottom: 1px solid #eee;
  display: flex;
  align-items: center;
}

.archive-list li:last-child {
  border-bottom: none;
}

.archive-list a {
  text-decoration: none;
  color: #0366d6;
  flex: 1;
}

.archive-list a:hover {
  text-decoration: underline;
}

.archive-list time {
  color: #888;
  margin-left: 20px;
  min-width: 80px;
}

.archive-list .categories {
  margin-left: 20px;
}

.archive-list .categories a {
  font-size: 0.9em;
  padding: 2px 8px;
  background: #f0f7ff;
  border-radius: 12px;
  margin-right: 5px;
}
</style>
