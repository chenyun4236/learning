---
layout: home
title: 技术学习笔记
description: 记录 Linux、数据库、C++、数学等学习笔记
---

<div class="home-container">
  <!-- 主内容区 -->
  <main class="main-content">
    
    <h1>📚 欢迎来到我的知识库</h1>
    <p class="description">这里是我学习技术的笔记整理，涵盖多个技术领域。</p>
    
    <section class="recent-posts">
      <h2>📈 最近更新</h2>
      {% for post in site.posts limit:5 %}
      <article class="post-item">
        <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
        <div class="post-meta">
          <time>{{ post.date | date: "%Y-%m-%d" }}</time>
          <span class="categories">
            {% for category in post.categories %}
            <a href="/categories/{{ category | slugify }}/">{{ category }}</a>
            {% unless forloop.last %}·{% endunless %}
            {% endfor %}
          </span>
        </div>
        <p>{{ post.excerpt | strip_html | truncate: 120 }}</p>
      </article>
      {% endfor %}
      <div class="view-all">
        <a href="/archive/" class="btn">查看所有文章 →</a>
      </div>
    </section>
    
  </main>
  
  <!-- 右侧边栏 -->
  <aside class="sidebar">
    
    <!-- 分类浏览 -->
    <section class="sidebar-section">
      <h3>📂 分类浏览</h3>
      <div class="categories-list">
        <a href="/categories/linux/" class="category-tag">
          <span class="emoji">🐧</span> Linux
          <small>系统命令、Shell脚本</small>
        </a>
        <a href="/categories/mysql/" class="category-tag">
          <span class="emoji">🗄️</span> MySQL
          <small>SQL优化、事务管理</small>
        </a>
        <a href="/categories/postgresql/" class="category-tag">
          <span class="emoji">🐘</span> PostgreSQL
          <small>JSONB、高级特性</small>
        </a>
        <a href="/categories/cpp/" class="category-tag">
          <span class="emoji">⚡</span> C++
          <small>STL、并发编程</small>
        </a>
        <a href="/categories/math/" class="category-tag">
          <span class="emoji">📐</span> 高等数学
          <small>微积分、线性代数</small>
        </a>
      </div>
    </section>
    
    <!-- 站点信息 -->
    <section class="sidebar-section">
      <h3>ℹ️ 站点信息</h3>
      <div class="site-info">
        <div class="author">
          <strong>ChenYun</strong>
          <p>chenyun4236@gmail.com</p>
        </div>
        <div class="tags">
          <span class="tag">Linux</span>
          <span class="tag">MySQL</span>
          <span class="tag">PostgreSQL</span>
          <span class="tag">C++</span>
          <span class="tag">高等数学</span>
          <span class="tag">编程笔记</span>
        </div>
        <div class="subscribe">
          <a href="/feed.xml" class="rss-link">
            📡 订阅 RSS
          </a>
        </div>
      </div>
    </section>
    
    <!-- 最新文章列表 -->
    <section class="sidebar-section">
      <h3>📝 最新文章</h3>
      <ul class="post-list">
        {% for post in site.posts limit:8 %}
        <li>
          <a href="{{ post.url }}">{{ post.title }}</a>
          <time>{{ post.date | date: "%m-%d" }}</time>
        </li>
        {% endfor %}
      </ul>
    </section>
    
  </aside>
</div>

<style>
/* 布局容器 */
.home-container {
  display: grid;
  grid-template-columns: 1fr 300px;
  gap: 40px;
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

/* 主内容区 */
.main-content {
  min-width: 0; /* 防止内容溢出 */
}

.main-content h1 {
  font-size: 2.2em;
  margin-bottom: 10px;
}

.description {
  color: #666;
  font-size: 1.1em;
  margin-bottom: 40px;
}

/* 文章列表 */
.recent-posts {
  margin-top: 40px;
}

.post-item {
  border-bottom: 1px solid #eee;
  padding: 20px 0;
}

.post-item h3 {
  margin: 0 0 8px 0;
  font-size: 1.3em;
}

.post-item h3 a {
  color: #0366d6;
  text-decoration: none;
}

.post-item h3 a:hover {
  text-decoration: underline;
}

.post-meta {
  display: flex;
  align-items: center;
  gap: 15px;
  color: #666;
  font-size: 0.9em;
  margin-bottom: 10px;
}

.post-meta time {
  color: #888;
}

.categories a {
  color: #0366d6;
  text-decoration: none;
  margin-right: 5px;
}

.categories a:hover {
  text-decoration: underline;
}

.view-all {
  text-align: center;
  margin-top: 30px;
}

.btn {
  display: inline-block;
  padding: 10px 25px;
  background: #0366d6;
  color: white;
  text-decoration: none;
  border-radius: 5px;
  font-weight: 500;
}

.btn:hover {
  background: #0251b3;
}

/* 侧边栏 */
.sidebar {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.sidebar-section {
  background: #f8f9fa;
  border-radius: 10px;
  padding: 20px;
  border: 1px solid #e9ecef;
}

.sidebar-section h3 {
  margin-top: 0;
  margin-bottom: 15px;
  font-size: 1.2em;
  color: #333;
}

/* 分类列表 */
.categories-list {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.category-tag {
  display: block;
  padding: 12px 15px;
  background: white;
  border: 1px solid #e1e4e8;
  border-radius: 8px;
  text-decoration: none;
  color: #24292e;
  transition: all 0.2s ease;
}

.category-tag:hover {
  background: #f6f8fa;
  border-color: #0366d6;
  transform: translateX(5px);
}

.category-tag .emoji {
  margin-right: 8px;
  font-size: 1.2em;
}

.category-tag small {
  display: block;
  color: #666;
  font-size: 0.85em;
  margin-top: 4px;
}

/* 站点信息 */
.site-info {
  font-size: 0.95em;
}

.author {
  margin-bottom: 15px;
}

.author strong {
  display: block;
  font-size: 1.1em;
  margin-bottom: 5px;
}

.author p {
  color: #666;
  margin: 0;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 5px;
  margin: 15px 0;
}

.tag {
  background: #e1e4e8;
  color: #24292e;
  padding: 3px 8px;
  border-radius: 12px;
  font-size: 0.85em;
}

.rss-link {
  display: inline-block;
  color: #ff6b35;
  text-decoration: none;
  font-weight: 500;
}

.rss-link:hover {
  text-decoration: underline;
}

/* 文章列表 */
.post-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.post-list li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 8px 0;
  border-bottom: 1px solid #eee;
}

.post-list li:last-child {
  border-bottom: none;
}

.post-list a {
  color: #0366d6;
  text-decoration: none;
  flex: 1;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  margin-right: 10px;
}

.post-list a:hover {
  text-decoration: underline;
}

.post-list time {
  color: #888;
  font-size: 0.85em;
  white-space: nowrap;
}

/* 响应式设计 */
@media (max-width: 992px) {
  .home-container {
    grid-template-columns: 1fr;
    gap: 30px;
  }
  
  .sidebar {
    grid-row: 1;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
  }
}

@media (max-width: 768px) {
  .home-container {
    padding: 15px;
  }
  
  .sidebar {
    grid-template-columns: 1fr;
  }
}
</style>
