---
layout: single
title: "博客"
permalink: /blog/
author_profile: true
classes: wide
---

<h1>博客文章</h1>
<p>在这里分享我的研究心得、学习笔记和项目经验。</p>

{% if site.posts.size > 0 %}
<div class="grid__wrapper">
  {% for post in site.posts %}
    <div class="grid__item">
      <article class="archive__item" itemscope itemtype="https://schema.org/CreativeWork">
        <h2 class="archive__item-title no_toc" itemprop="headline">
          <a href="{{ post.url | relative_url }}" rel="permalink">{{ post.title }}</a>
        </h2>
        <p class="page__meta">
          <i class="far fa-calendar-alt" aria-hidden="true"></i> {{ post.date | date: "%Y年%m月%d日" }}
          {% if post.categories %}
            <i class="fas fa-folder-open" aria-hidden="true" style="margin-left:10px;"></i>
            {% for category in post.categories %}
              <span class="page__meta-category">{{ category }}</span>{% unless forloop.last %}, {% endunless %}
            {% endfor %}
          {% endif %}
        </p>
        {% if post.excerpt %}
          <p class="archive__item-excerpt" itemprop="description">{{ post.excerpt | markdownify | strip_html | truncate: 200 }}</p>
        {% endif %}
        <p><a href="{{ post.url | relative_url }}" class="btn btn--primary">阅读全文</a></p>
      </article>
    </div>
  {% endfor %}
</div>
{% else %}
<p>还没有发布任何文章。敬请期待！</p>
{% endif %}
