---
layout: single
title: "Blog"
permalink: /blog/
author_profile: true
---

## 📝 博客文章

在这里分享我的研究心得、学习笔记和项目经验。

{% if site.posts.size > 0 %}
<div class="blog-posts">
  {% for post in site.posts %}
  <article class="blog-post">
    <h2>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h2>
    
    <div class="post-meta">
      <span class="post-date">
        <i class="far fa-calendar"></i> {{ post.date | date: "%Y年%m月%d日" }}
      </span>
      {% if post.categories %}
      <span class="post-categories">
        <i class="far fa-folder"></i>
        {% for category in post.categories %}
          <span class="category">{{ category }}</span>{% unless forloop.last %}, {% endunless %}
        {% endfor %}
      </span>
      {% endif %}
    </div>
    
    <div class="post-excerpt">
      {% if post.excerpt %}
        {{ post.excerpt }}
      {% else %}
        {{ post.content | strip_html | truncatewords: 50 }}
      {% endif %}
    </div>
    
    <a href="{{ post.url | relative_url }}" class="read-more">阅读全文 →</a>
  </article>
  <hr>
  {% endfor %}
</div>
{% else %}
<p>还没有发布任何文章。敬请期待！</p>
{% endif %}

<!-- 添加一些CSS样式 -->
<style>
.blog-post {
  margin-bottom: 3rem;
  padding: 1.5rem;
  border-radius: 8px;
  transition: all 0.3s ease;
}

.blog-post:hover {
  background-color: #f8f9fa;
  transform: translateY(-2px);
}

.post-meta {
  color: #6c757d;
  font-size: 0.9rem;
  margin-bottom: 1rem;
}

.post-meta i {
  margin-right: 5px;
}

.category {
  background-color: #e9ecef;
  padding: 2px 8px;
  border-radius: 4px;
  font-size: 0.8rem;
  margin-right: 5px;
}

.post-excerpt {
  color: #495057;
  line-height: 1.6;
  margin-bottom: 1rem;
}

.read-more {
  color: #007bff;
  text-decoration: none;
  font-weight: 500;
}

.read-more:hover {
  text-decoration: underline;
}
</style>
