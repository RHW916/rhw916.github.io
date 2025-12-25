layout: single
title: "Blog"
title: "博客"
permalink: /blog/
author_profile: true
---
@@ -10,89 +10,241 @@ author_profile: true
在这里分享我的研究心得、学习笔记和项目经验。

{% if site.posts.size > 0 %}
<div class="blog-posts">
<div class="blog-container">
  {% for post in site.posts %}
  <article class="blog-post">
    <h2>
  <article class="blog-card">
    
    <!-- 文章标题 -->
    <h2 class="blog-title">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h2>

    <div class="post-meta">
      <span class="post-date">
    <!-- 元信息：作者、日期 -->
    <div class="blog-meta">
      <span class="meta-author">
        <i class="fas fa-user"></i> {{ site.author.name }}
      </span>
      <span class="meta-date">
        <i class="far fa-calendar"></i> {{ post.date | date: "%Y年%m月%d日" }}
      </span>
    </div>
    
    <!-- 分类与标签 -->
    <div class="blog-taxonomy">
      {% if post.categories %}
      <span class="post-categories">
        <i class="far fa-folder"></i>
      <div class="taxonomy-section">
        <span class="taxonomy-label"><i class="far fa-folder"></i> 分类：</span>
        {% for category in post.categories %}
          <span class="category">{{ category }}</span>{% unless forloop.last %}, {% endunless %}
        <span class="category-badge">{{ category }}</span>
        {% endfor %}
      </span>
      </div>
      {% endif %}
      
      {% if post.tags %}
      <div class="taxonomy-section">
        <span class="taxonomy-label"><i class="fas fa-tags"></i> 标签：</span>
        {% for tag in post.tags %}
        <span class="tag-badge">#{{ tag }}</span>
        {% endfor %}
      </div>
      {% endif %}
    </div>

    <div class="post-excerpt">
    <!-- 文章摘要 -->
    <div class="blog-excerpt">
      {% if post.excerpt %}
        {{ post.excerpt }}
      {% else %}
        {{ post.content | strip_html | truncatewords: 50 }}
        {{ post.content | strip_html | truncatewords: 60 }}
      {% endif %}
    </div>

    <a href="{{ post.url | relative_url }}" class="read-more">阅读全文 →</a>
    <!-- 阅读全文链接 -->
    <a href="{{ post.url | relative_url }}" class="read-more-button">
      阅读全文 <i class="fas fa-arrow-right"></i>
    </a>
    
  </article>
  <hr>
  {% endfor %}
</div>

{% else %}
<p>还没有发布任何文章。敬请期待！</p>
<!-- 无文章时的提示 -->
<div class="empty-blog">
  <p><i class="far fa-edit fa-2x"></i></p>
  <p>还没有发布任何文章。敬请期待！</p>
</div>
{% endif %}

<!-- 添加一些CSS样式 -->
<style>
.blog-post {
  margin-bottom: 3rem;
  padding: 1.5rem;
  border-radius: 8px;
  transition: all 0.3s ease;
/* 容器与卡片 */
.blog-container {
  max-width: 900px;
  margin: 0 auto;
}
.blog-card {
  background: white;
  border-radius: 12px;
  padding: 2rem;
  margin-bottom: 2.5rem;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
  border: 1px solid #eaeaea;
  transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
}
.blog-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.1);
  border-color: #3b82f6;
}

.blog-post:hover {
  background-color: #f8f9fa;
  transform: translateY(-2px);
/* 标题 */
.blog-title {
  margin-top: 0;
  margin-bottom: 0.75rem;
  font-size: 1.5rem;
  line-height: 1.3;
}
.blog-title a {
  color: #1e293b;
  text-decoration: none;
  background: linear-gradient(to right, #3b82f6, #3b82f6) no-repeat right bottom;
  background-size: 0 2px;
  transition: background-size 0.3s, color 0.3s;
}
.blog-title a:hover {
  color: #3b82f6;
  background-size: 100% 2px;
  background-position: left bottom;
}

.post-meta {
  color: #6c757d;
  font-size: 0.9rem;
/* 元信息 */
.blog-meta {
  display: flex;
  flex-wrap: wrap;
  gap: 1.2rem;
  margin-bottom: 1rem;
  color: #64748b;
  font-size: 0.9rem;
}

.post-meta i {
  margin-right: 5px;
.meta-author, .meta-date {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
}
.blog-meta i {
  color: #94a3b8;
}

.category {
  background-color: #e9ecef;
  padding: 2px 8px;
  border-radius: 4px;
  font-size: 0.8rem;
  margin-right: 5px;
/* 分类与标签 */
.blog-taxonomy {
  margin-bottom: 1.2rem;
}
.taxonomy-section {
  display: flex;
  align-items: flex-start;
  flex-wrap: wrap;
  margin-bottom: 0.6rem;
}
.taxonomy-label {
  color: #64748b;
  font-size: 0.9rem;
  margin-right: 0.6rem;
  white-space: nowrap;
  margin-top: 0.2rem;
}
.taxonomy-label i {
  margin-right: 0.3rem;
}
.category-badge, .tag-badge {
  display: inline-block;
  padding: 0.35rem 0.85rem;
  margin: 0.2rem 0.4rem 0.2rem 0;
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 500;
  line-height: 1;
  transition: all 0.2s;
}
.category-badge {
  background-color: #e0f2fe;
  color: #0369a1;
  border: 1px solid #bae6fd;
}
.category-badge:hover {
  background-color: #bae6fd;
  transform: scale(1.05);
}
.tag-badge {
  background-color: #f3e8ff;
  color: #7c3aed;
  border: 1px solid #e9d5ff;
}
.tag-badge:hover {
  background-color: #e9d5ff;
  transform: scale(1.05);
}

.post-excerpt {
  color: #495057;
  line-height: 1.6;
  margin-bottom: 1rem;
/* 摘要 */
.blog-excerpt {
  color: #475569;
  line-height: 1.7;
  margin-bottom: 1.5rem;
  font-size: 1rem;
}

.read-more {
  color: #007bff;
/* 阅读全文按钮 */
.read-more-button {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.6rem 1.5rem;
  background: linear-gradient(to right, #3b82f6, #2563eb);
  color: white;
  text-decoration: none;
  border-radius: 8px;
  font-weight: 500;
  font-size: 0.95rem;
  transition: all 0.3s;
  border: none;
  cursor: pointer;
}
.read-more-button:hover {
  transform: translateX(5px);
  box-shadow: 0 5px 15px rgba(37, 99, 235, 0.3);
  color: white;
  text-decoration: none;
}

/* 无文章状态 */
.empty-blog {
  text-align: center;
  padding: 4rem 2rem;
  color: #64748b;
}
.empty-blog i {
  margin-bottom: 1rem;
  color: #cbd5e1;
}

.read-more:hover {
  text-decoration: underline;
/* 响应式调整 */
@media (max-width: 768px) {
  .blog-card {
    padding: 1.5rem;
    margin-bottom: 2rem;
  }
  .blog-title {
    font-size: 1.3rem;
  }
  .blog-meta {
    flex-direction: column;
    gap: 0.5rem;
  }
  .taxonomy-section {
    flex-direction: column;
    align-items: flex-start;
  }
  .taxonomy-label {
    margin-bottom: 0.4rem;
  }
}
</style>
