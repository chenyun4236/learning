---
layout: custom
title: 学习笔记
---

<div class="blog-container">
  <!-- 主内容区（左侧） -->
  <main class="blog-main">
    
    <header class="blog-header">
      <h1>📚 技术学习笔记</h1>
      <p class="blog-description">记录 Linux、数据库、C++、数学等学习笔记，持续更新中...</p>
    </header>
    
    <section class="featured-categories">
      <h2>📂 分类浏览</h2>
      <div class="categories-grid">
        <a href="/learning/categories/linux/" class="category-card">
          <span class="category-icon">🐧</span>
          <div>
            <h3>Linux</h3>
            <p>系统命令、Shell脚本、运维知识</p>
          </div>
        </a>
        
        <a href="/learning/categories/mysql/" class="category-card">
          <span class="category-icon">🗄️</span>
          <div>
            <h3>MySQL</h3>
            <p>数据库设计、SQL优化、事务管理</p>
          </div>
        </a>
        
        <a href="/learning/categories/postgresql/" class="category-card">
          <span class="category-icon">🐘</span>
          <div>
            <h3>PostgreSQL</h3>
            <p>高级特性、JSONB、空间数据</p>
          </div>
        </a>
        
        <a href="/learning/categories/cpp/" class="category-card">
          <span class="category-icon">⚡</span>
          <div>
            <h3>C++</h3>
            <p>语法特性、STL、并发编程</p>
          </div>
        </a>
        
        <a href="/learning/categories/math/" class="category-card">
          <span class="category-icon">📐</span>
          <div>
            <h3>高等数学</h3>
            <p>微积分、线性代数、概率统计</p>
          </div>
        </a>
      </div>
    </section>
    
    <section class="recent-posts">
      <h2>📝 最新文章</h2>
      {% for post in site.posts limit:10 %}
      <article class="post-card">
        <div class="post-meta">
          <time datetime="{{ post.date | date_to_xmlschema }}">
            {{ post.date | date: "%Y年%m月%d日" }}
          </time>
          <span class="post-categories">
            {% for category in post.categories %}
            <a href="/learning/categories/{{ category | slugify }}/" class="category-badge">{{ category }}</a>
            {% endfor %}
          </span>
        </div>
        <h3 class="post-title">
          <a href="{{ post.url }}">{{ post.title }}</a>
        </h3>
        <p class="post-excerpt">
          {{ post.excerpt | strip_html | truncate: 180 }}
        </p>
        <div class="post-footer">
          <a href="{{ post.url }}" class="read-more">阅读全文 →</a>
        </div>
      </article>
      {% endfor %}
    </section>
    
  </main>
</div>

<style>
/* 基础布局 */
.blog-container {
  display: grid;
  grid-template-columns: 1fr 280px;
  gap: 40px;
  max-width: 1200px;
  margin: 0 auto;
  padding: 30px 20px;
}

/* 主内容区 */
.blog-main {
  min-width: 0;
}

.blog-header {
  margin-bottom: 40px;
  padding-bottom: 20px;
  border-bottom: 1px solid #eaeaea;
}

.blog-header h1 {
  font-size: 2.4em;
  margin: 0 0 10px 0;
  color: #333;
}

.blog-description {
  color: #666;
  font-size: 1.1em;
  line-height: 1.6;
  margin: 0;
}

/* 分类浏览 */
.featured-categories {
  margin-bottom: 50px;
}

.featured-categories h2 {
  font-size: 1.6em;
  margin-bottom: 20px;
  color: #444;
  padding-bottom: 10px;
  border-bottom: 2px solid #f0f0f0;
}

.categories-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 20px;
}

.category-card {
  display: flex;
  align-items: center;
  padding: 20px;
  background: #fff;
  border: 1px solid #e8e8e8;
  border-radius: 8px;
  text-decoration: none;
  color: inherit;
  transition: all 0.3s ease;
}

.category-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 5px 20px rgba(0,0,0,0.08);
  border-color: #0366d6;
}

.category-icon {
  font-size: 2em;
  margin-right: 15px;
}

.category-card h3 {
  margin: 0 0 5px 0;
  font-size: 1.2em;
  color: #333;
}

.category-card p {
  margin: 0;
  color: #666;
  font-size: 0.9em;
  line-height: 1.4;
}

/* 文章卡片 */
.recent-posts h2 {
  font-size: 1.6em;
  margin-bottom: 25px;
  color: #444;
  padding-bottom: 10px;
  border-bottom: 2px solid #f0f0f0;
}

.post-card {
  background: #fff;
  border: 1px solid #e8e8e8;
  border-radius: 8px;
  padding: 25px;
  margin-bottom: 25px;
  transition: all 0.3s ease;
}

.post-card:hover {
  box-shadow: 0 5px 15px rgba(0,0,0,0.05);
  border-color: #d0d7de;
}

.post-meta {
  display: flex;
  align-items: center;
  margin-bottom: 12px;
  font-size: 0.9em;
  color: #666;
}

.post-meta time {
  color: #888;
}

.post-categories {
  margin-left: 15px;
}

.category-badge {
  display: inline-block;
  padding: 3px 10px;
  background: #f0f7ff;
  color: #0366d6;
  border-radius: 12px;
  font-size: 0.85em;
  text-decoration: none;
  margin-right: 5px;
}

.category-badge:hover {
  background: #0366d6;
  color: white;
}

.post-title {
  margin: 0 0 15px 0;
  font-size: 1.4em;
}

.post-title a {
  color: #333;
  text-decoration: none;
}

.post-title a:hover {
  color: #0366d6;
}

.post-excerpt {
  color: #555;
  line-height: 1.6;
  margin: 0 0 20px 0;
}

.post-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.read-more {
  color: #0366d6;
  text-decoration: none;
  font-weight: 500;
}

.read-more:hover {
  text-decoration: underline;
}

/* 右侧边栏 */
.blog-sidebar {
  position: sticky;
  top: 30px;
  height: fit-content;
}

/* 侧边栏通用样式 */
.sidebar-section {
  background: #fff;
  border: 1px solid #e8e8e8;
  border-radius: 8px;
  padding: 20px;
  margin-bottom: 25px;
}

.sidebar-section h3 {
  margin: 0 0 15px 0;
  font-size: 1.1em;
  color: #333;
  padding-bottom: 10px;
  border-bottom: 1px solid #f0f0f0;
}

/* 网站信息 */
.site-info {
  font-size: 0.95em;
  line-height: 1.6;
}

.site-info p {
  margin: 8px 0;
}

/* 热门分类 */
.popular-categories {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.popular-category {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 8px 12px;
  background: #f8f9fa;
  border-radius: 6px;
  text-decoration: none;
  color: #333;
  transition: all 0.2s ease;
}

.popular-category:hover {
  background: #0366d6;
  color: white;
}

.category-name {
  font-size: 0.95em;
}

.category-count {
  background: rgba(0,0,0,0.1);
  padding: 2px 8px;
  border-radius: 10px;
  font-size: 0.85em;
}

.popular-category:hover .category-count {
  background: rgba(255,255,255,0.2);
}

/* 归档 */
.archives {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.archive-year {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 8px 12px;
  color: #555;
  text-decoration: none;
  border-radius: 6px;
  transition: all 0.2s ease;
}

.archive-year:hover {
  background: #f0f7ff;
  color: #0366d6;
}

.archive-year span {
  color: #888;
  font-size: 0.9em;
}

/* 标签云 */
.tag-cloud {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.tag-item {
  display: inline-block;
  padding: 6px 12px;
  background: #f6f8fa;
  color: #555;
  border-radius: 15px;
  text-decoration: none;
  font-size: 0.9em;
  transition: all 0.2s ease;
  border: 1px solid #e1e4e8;
}

.tag-item:hover {
  background: #0366d6;
  color: white;
  border-color: #0366d6;
  transform: translateY(-2px);
}

/* 响应式设计 */
@media (max-width: 992px) {
  .blog-container {
    grid-template-columns: 1fr;
    gap: 30px;
  }
  
  .blog-sidebar {
    position: static;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
  }
}

@media (max-width: 768px) {
  .blog-container {
    padding: 20px 15px;
  }
  
  .categories-grid {
    grid-template-columns: 1fr;
  }
  
  .post-card {
    padding: 20px;
  }
  
  .sidebar-section {
    padding: 15px;
  }
}

@media (max-width: 480px) {
  .blog-header h1 {
    font-size: 2em;
  }
  
  .post-title {
    font-size: 1.2em;
  }
}
</style>
