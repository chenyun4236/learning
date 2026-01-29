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
          <a href="{{ site.baseurl }}/categories/{{ details[1] }}/" class="category-card">
            <span class="category-icon">{{ details[2] }}</span>
            <div class="category-info">
              <h3>{{ details[0] }}</h3>
            </div>
          </a>
        {% endfor %}
      </div>
    </section>

    <!-- 最近更新（分页） -->
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
          <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
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
          <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">
            阅读全文 →
          </a>
        </div>
      </article>
      {% endfor %}

      <!-- 分页导航 -->
      {% if paginator.total_pages > 1 %}
      <nav class="pagination">
        {% if paginator.previous_page %}
          <a class="page-btn" href="{{ site.baseurl }}{{ paginator.previous_page_path }}">← 上一页</a>
        {% endif %}

        <span class="page-info">
          第 {{ paginator.page }} / {{ paginator.total_pages }} 页
        </span>

        {% if paginator.next_page %}
          <a class="page-btn" href="{{ site.baseurl }}{{ paginator.next_page_path }}">下一页 →</a>
        {% endif %}
      </nav>
      {% endif %}
    </section>

  </main>
</div>

<style>
:root {
  --primary-color: #0366d6;
  --bg-color: #f6f8fa;
  --text-main: #24292f;
  --text-muted: #57606a;
  --card-shadow: 0 3px 12px rgba(0,0,0,0.07);
}

.blog-container {
  max-width: 900px;
  margin: 0 auto;
  padding: 40px 20px;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
}

.blog-header {
  text-align: center;
  margin-bottom: 50px;
}

.blog-header h1 {
  font-size: 2.5rem;
  font-weight: 800;
  margin-bottom: 15px;
}

.search-area {
  margin-top: 25px;
  max-width: 500px;
  margin-left: auto;
  margin-right: auto;
}

#search-input {
  width: 100%;
  padding: 12px 20px;
  border-radius: 25px;
  border: 1px solid #d0d7de;
  transition: all 0.3s ease;
}

#search-input:focus {
  border-color: var(--primary-color);
  box-shadow: 0 0 0 3px rgba(3, 102, 214, 0.2);
}

.categories-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
  gap: 15px;
  margin-bottom: 60px;
}

.category-card {
  text-align: center;
  padding: 20px;
  background: #fff;
  border-radius: 12px;
  box-shadow: var(--card-shadow);
  transition: all 0.2s;
  text-decoration: none;
}

.category-card:hover {
  transform: translateY(-5px);
  background: var(--primary-color);
}

.category-card:hover h3,
.category-card:hover .category-icon {
  color: #fff;
}

.category-icon {
  font-size: 1.8rem;
  margin-bottom: 8px;
}

.post-card {
  background: #fff;
  border-radius: 12px;
  padding: 30px;
  margin-bottom: 25px;
  box-shadow: var(--card-shadow);
  transition: all 0.3s ease;
}

.post-card:hover {
  transform: translateX(6px);
}

.pagination {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 40px;
}

.page-btn {
  text-decoration: none;
  font-weight: 600;
  color: var(--primary-color);
}
</style>
