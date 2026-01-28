---
layout: home
title: 技术学习笔记
description: 记录 Linux、数据库、C++、数学等学习笔记
---

# 📚 欢迎来到我的知识库

这里是我学习技术的笔记整理，涵盖多个技术领域。

## 📂 分类浏览

<div class="categories-grid">
  <a href="/categories/linux/" class="category-card">
    <h3>🐧 Linux</h3>
    <p>系统命令、Shell脚本、运维知识</p>
  </a>
  
  <a href="/categories/mysql/" class="category-card">
    <h3>🗄️ MySQL</h3>
    <p>数据库设计、SQL优化、事务管理</p>
  </a>
  
  <a href="/categories/postgresql/" class="category-card">
    <h3>🐘 PostgreSQL</h3>
    <p>高级特性、JSONB、空间数据</p>
  </a>
  
  <a href="/categories/cpp/" class="category-card">
    <h3>⚡ C++</h3>
    <p>语法特性、STL、并发编程</p>
  </a>
  
  <a href="/categories/math/" class="category-card">
    <h3>📐 高等数学</h3>
    <p>微积分、线性代数、概率统计</p>
  </a>
</div>

## 📈 最近更新

{% for post in site.posts limit:8 %}
<div class="post-preview">
  <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
  <div class="post-meta">
    <span>{{ post.date | date: "%Y-%m-%d" }}</span>
    <span>|</span>
    <span>{% for category in post.categories %}<a href="/categories/{{ category | slugify }}/">{{ category }}</a>{% unless forloop.last %}, {% endunless %}{% endfor %}</span>
  </div>
  <p>{{ post.excerpt | strip_html | truncate: 200 }}</p>
</div>
{% endfor %}

<p style="text-align: center; margin-top: 40px;">
  <a href="/archive/" class="btn">查看所有文章 →</a>
</p>

<style>
.categories-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  margin: 40px 0;
}
.category-card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 20px;
  text-decoration: none;
  color: inherit;
  transition: transform 0.3s, box-shadow 0.3s;
}
.category-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0,0,0,0.1);
}
.post-preview {
  border-bottom: 1px solid #eee;
  padding: 20px 0;
}
.post-meta {
  color: #666;
  font-size: 0.9em;
  margin: 5px 0;
}
.btn {
  display: inline-block;
  padding: 10px 20px;
  background: #0366d6;
  color: white;
  text-decoration: none;
  border-radius: 5px;
}
</style>
