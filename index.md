---
layout: custom
title: 学习笔记
---

<div class="blog-container">
  <main class="blog-main">
    
    <header class="blog-header">
      <h1>📚 技术学习笔记</h1>
      <p class="blog-description">记录 Linux、数据库、C++、数学等学习笔记，持续更新中...</p>
      
      <div class="search-area">
        <input type="text" id="search-input" placeholder="🔍 搜索笔记文章...">
      </div>
    </header>
    
    <section class="featured-categories">
      <div class="section-title">
        <h2>📂 分类浏览</h2>
      </div>
      <div class="categories-grid">
        {% assign categories = "Linux,linux,🐧;MySQL,mysql,🐬;PostgreSQL,postgresql,🐘;C++,cpp,⚡;高等数学,math,📐" | split: ";" %}
        {% for cat in categories %}
          {% assign details = cat | split: "," %}
          <a href="/learning/categories/{{ details[1] }}/" class="category-card">
            <span class="category-icon">{{ details[2] }}</span>
            <div class="category-info">
              <h3>{{ details[0] }}</h3>
            </div>
          </a>
        {% endfor %}
      </div>
    </section>
    
    <section class="recent-posts">
      <div class="section-title">
        <h2>📝 最近更新</h2>
      </div>
      
      {% for post in site.posts limit:10 %}
      <article class="post-card">
        <div class="post-meta">
          <time datetime="{{ post.date | date_to_xmlschema }}">
            📅 {{ post.date | date: "%Y-%m-%d" }}
          </time>
          <span class="read-time">☕ {{ post.content | strip_html | size | divided_by: 400 | plus: 1 }} min read</span>
        </div>
        
        <h3 class="post-title">
          <a href="{{ post.url }}">{{ post.title }}</a>
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
          <a href="{{ post.url }}" class="read-more">阅读全文 →</a>
        </div>
      </article>
      {% endfor %}
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

/* 基础布局 */
.blog-container {
  max-width: 900px; /* 缩小宽度，提升长文阅读体验 */
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
  color: var(--text-main);
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
  background: #fff;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  outline: none;
}

#search-input:focus {
  border-color: var(--primary-color);
  box-shadow: 0 0 0 3px rgba(3, 102, 214, 0.2);
  width: 110%; /* 聚焦时稍微拉长 */
  margin-left: -5%;
}

/* 标题样式优化 */
.section-title {
  display: flex;
  align-items: center;
  margin-bottom: 25px;
}

.section-title h2 {
  font-size: 1.5rem;
  color: var(--text-main);
  position: relative;
}

/* 分类卡片：改为更紧凑的横向平铺 */
.categories-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
  gap: 15px;
  margin-bottom: 60px;
}

.category-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
  background: #fff;
  border-radius: 12px;
  text-decoration: none;
  transition: all 0.2s;
  box-shadow: var(--card-shadow);
}

.category-card:hover {
  transform: translateY(-5px);
  background: var(--primary-color);
}

.category-card:hover h3, .category-card:hover .category-icon {
  color: #fff;
}

.category-icon {
  font-size: 1.8rem;
  margin-bottom: 8px;
}

.category-card h3 {
  margin: 0;
  font-size: 1rem;
  color: var(--text-main);
}

/* 文章卡片优化 */
.post-card {
  background: #fff;
  border-radius: 12px;
  padding: 30px;
  margin-bottom: 25px;
  box-shadow: var(--card-shadow);
  transition: all 0.3s ease;
  border-left: 0 solid var(--primary-color);
}

.post-card:hover {
  border-left-width: 6px;
  transform: translateX(8px);
}

.post-meta {
  font-size: 0.85rem;
  color: var(--text-muted);
  margin-bottom: 12px;
  display: flex;
  gap: 15px;
}

.post-title {
  margin: 0 0 15px 0;
  font-size: 1.6rem;
}

.post-title a {
  color: var(--text-main);
  text-decoration: none;
  background-image: linear-gradient(120deg, rgba(3, 102, 214, 0.1) 0%, rgba(3, 102, 214, 0.1) 100%);
  background-repeat: no-repeat;
  background-size: 100% 0.2em;
  background-position: 0 88%;
  transition: background-size 0.25s ease-in;
}

.post-title a:hover {
  background-size: 100% 88%;
}

.post-excerpt {
  color: #444;
  line-height: 1.7;
  font-size: 1.05rem;
  margin-bottom: 20px;
}

.post-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 15px;
  border-top: 1px solid #f0f0f0;
}

.category-badge {
  background: #eff6ff;
  color: var(--primary-color);
  padding: 4px 12px;
  border-radius: 6px;
  font-size: 0.8rem;
  font-weight: 600;
  margin-right: 8px;
}

.read-more {
  font-weight: 600;
  color: var(--primary-color);
  text-decoration: none;
}

/* 响应式 */
@media (max-width: 768px) {
  .blog-container { padding: 20px; }
  .post-card:hover { transform: none; }
  #search-input:focus { width: 100%; margin-left: 0; }
}
</style>
