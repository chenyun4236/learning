---
layout: custom
title: 学习笔记
---

<div class="blog-container">
  <main class="blog-main">

    <header class="blog-header">
      <h1>📚 技术学习笔记</h1>
      <p class="blog-description">
        记录 Linux、数据库、C++、数学等学习笔记，持续更新中...
      </p>

      <div class="search-area">
        <input type="text" id="search-input" placeholder="🔍 搜索笔记文章...">
      </div>
    </header>

    <!-- 分类浏览 -->
    <section class="featured-categories">
      <div class="section-title">
        <h2>📂 分类浏览</h2>
      </div>

      <div class="categories-grid">
        {% assign categories = "Linux,linux,🐧;MySQL,mysql,🐬;PostgreSQL,postgresql,🐘;C++,cpp,⚡;高等数学,math,📐" | split: ";" %}
        {% for cat in categories %}
          {% assign details = cat | split: "," %}
          <a href="{{ '/categories/' | append: details[1] | append: '/' | relative_url }}"
             class="category-card">
            <span class="category-icon">{{ details[2] }}</span>
            <div class="category-info">
              <h3>{{ details[0] }}</h3>
            </div>
          </a>
        {% endfor %}
      </div>
    </section>

    <!-- 最近更新 -->
    <section class="recent-posts">
      <div class="section-title">
        <h2>📝 最近更新</h2>
      </div>

      {% for post in paginator.posts %}
      <article class="post-card">
        <div class="post-meta">
          <time datetime="{{ post.date | date_to_xmlschema }}">
            📅 {{ post.date | date: "%Y-%m-%d" }}
          </time>
          <span class="read-time">
            ☕ {{ post.content | strip_html | size | divided_by: 400 | plus: 1 }} min read
          </span>
        </div>

        <h3 class="post-title">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h3>

        <p class="post-excerpt">
          {{ post.excerpt | strip_html | truncate: 150 }}
        </p>

        <div class="post-footer">
          <div class="post-tags">
            {% for category in post.categories %}
              <span class="category-badge">{{ category }}</span>
            {% endfor %}
          </div>
          <a href="{{ post.url | relative_url }}" class="read-more">
            阅读全文 →
          </a>
        </div>
      </article>
      {% endfor %}

      <!-- 分页 -->
      {% if paginator.total_pages > 1 %}
      <nav class="pagination">
        {% if paginator.previous_page %}
          <a class="page-btn" href="{{ paginator.previous_page_path | relative_url }}">
            ← 上一页
          </a>
        {% endif %}

        <span class="page-info">
          第 {{ paginator.page }} / {{ paginator.total_pages }} 页
        </span>

        {% if paginator.next_page %}
          <a class="page-btn" href="{{ paginator.next_page_path | relative_url }}">
            下一页 →
          </a>
        {% endif %}
      </nav>
      {% endif %}
    </section>

  </main>
</div>
