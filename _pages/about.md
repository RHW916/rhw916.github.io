---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<span class='anchor' id='about-me'></span>

## 👋 关于我

我是北京邮电大学理学院数学与应用数学专业的本科生。[<span class="resume-download">
  简历下载：
  <a href="/assets/pdf/CV_CN.pdf" target="_blank" class="cv-link">中文版 →</a>
  <a href="/assets/pdf/CV_EN.pdf" target="_blank" class="cv-link">English →</a>
</span>] 我的研究兴趣集中在**人工智能、多智能体系统和大语言模型优化**等领域。

### 🔬 研究方向
1. **多智能体系统与分布式计算**
   - 拜占庭鲁棒的协同定位与目标跟踪
   - 分布式算法设计与分析
   - 网络安全与容错机制

2. **机器学习与模型优化**
   - 大语言模型压缩与高效微调
   - 低资源场景下的模型适配
   - 时序数据分析与预测

3. **信号处理与神经科学**
   - 脑电信号频域分析
   - 神经信号解码与应用
   - 医学数据分析


My research interest includes neural machine translation and computer vision. I have published more than 100 papers at the top international AI conferences with total <a href='https://scholar.google.com/citations?user=DhtAFkwAAAAJ'>google scholar citations <strong><span id='total_cit'>260000+</span></strong></a> (You can also use google scholar badge <a href='https://scholar.google.com/citations?user=DhtAFkwAAAAJ'><img src="https://img.shields.io/endpoint?url={{ url | url_encode }}&logo=Google%20Scholar&labelColor=f6f6f6&color=9cf&style=flat&label=citations"></a>).


# 🔥 News
- *2022.02*: &nbsp;🎉🎉 Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet. 
- *2022.02*: &nbsp;🎉🎉 Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet.

<span class='anchor' id='blogs'></span>
# 📝 Blogs

在这里分享我的研究心得、学习笔记和项目经验。

## 🔬 最新博客文章

{% for post in site.posts limit:3 %}
<div class='paper-box'>
<div class='paper-box-text' markdown="1">

### [{{ post.title }}]({{ post.url | relative_url }})

<div style="margin-bottom: 12px; color: #666; font-size: 0.9rem;">
  <!-- 作者与日期 -->
  <span style="font-weight: bold; color: #333;">{{ site.author.name }}</span>
  <span style="margin: 0 10px;">|</span>
  <span>{{ post.date | date: "%Y年%m月%d日" }}</span>
</div>

<!-- 分类显示：循环所有，不加限制 -->
{% if post.categories %}
<div style="margin-bottom: 8px;">
  <span style="color: #666; font-size: 0.9rem;">分类：</span>
  {% for category in post.categories %}
  <span style="display: inline-block; background-color: #e5e7eb; color: #374151; padding: 4px 10px; margin: 2px 5px 2px 0; border-radius: 12px; font-size: 0.85rem; line-height: 1;">
    {{ category }}
  </span>
  {% endfor %}
</div>
{% endif %}

<!-- 标签显示：循环所有 -->
{% if post.tags %}
<div style="margin-bottom: 12px;">
  <span style="color: #666; font-size: 0.9rem;">标签：</span>
  {% for tag in post.tags %}
  <span style="display: inline-block; background-color: #dbeafe; color: #1e40af; padding: 4px 10px; margin: 2px 5px 2px 0; border-radius: 12px; font-size: 0.85rem; line-height: 1;">
    #{{ tag }}
  </span>
  {% endfor %}
</div>
{% endif %}

<!-- 文章摘要 -->
<div style="color: #4b5563; line-height: 1.6; margin-bottom: 15px;">
{{ post.excerpt | default: post.content | strip_html | truncatewords: 50 }}
</div>

<!-- 阅读全文链接 -->
<p>
<a href="{{ post.url | relative_url }}" style="color: #3b82f6; font-weight: 500; text-decoration: none; font-size: 0.95rem;">
阅读全文 →
</a>
</p>

</div>
</div>
{% endfor %}

<!-- 提示语和链接 -->
{% if site.posts.size == 0 %}
<p>目前还没有博客文章，敬请期待！</p>
{% endif %}

<p style="text-align: center; margin-top: 2rem;">
<a href="/blog/" style="display: inline-block; padding: 0.6rem 1.5rem; background-color: #3b82f6; color: white; text-decoration: none; border-radius: 6px; font-weight: 500;">
查看所有博客文章 →
</a>
</p>

<style>
/* 卡片整体样式 */
.paper-box {
  background: white;
  border-radius: 10px;
  padding: 1.8rem;
  margin-bottom: 2.5rem;
  box-shadow: 0 3px 12px rgba(0, 0, 0, 0.06);
  border-left: 4px solid #3b82f6;
  transition: all 0.3s ease;
}
.paper-box:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
}
.paper-box-text h4 {
  margin-top: 0;
  margin-bottom: 0.8rem;
  font-size: 1.3rem;
}
.paper-box-text h4 a {
  color: #1e3a8a;
  text-decoration: none;
}
.paper-box-text h4 a:hover {
  color: #3b82f6;
}
</style>

# 📝 Publications 

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">CVPR 2016</div><img src='images/500x300.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[Deep Residual Learning for Image Recognition](https://openaccess.thecvf.com/content_cvpr_2016/papers/He_Deep_Residual_Learning_CVPR_2016_paper.pdf)

**Kaiming He**, Xiangyu Zhang, Shaoqing Ren, Jian Sun

[**Project**](https://scholar.google.com/citations?view_op=view_citation&hl=zh-CN&user=DhtAFkwAAAAJ&citation_for_view=DhtAFkwAAAAJ:ALROH1vI_8AC) <strong><span class='show_paper_citations' data='DhtAFkwAAAAJ:ALROH1vI_8AC'></span></strong>
- Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet. 
</div>
</div>

- [Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet](https://github.com), A, B, C, **CVPR 2020**

# 🎖 Honors and Awards
- *2021.10* Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet. 
- *2021.09* Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet. 

# 📖 Educations
- *2019.06 - 2022.04 (now)*, Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet. 
- *2015.09 - 2019.06*, Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet. 

<!-- # 💬 Invited Talks
#- *2021.06*, Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet. 
- *2021.03*, Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus ornare aliquet ipsum, ac tempus justo dapibus sit amet.  \| [\[video\]](https://github.com/) -->
# 💻 Internships
- *2019.05 - 2020.02*, [Lorem](https://github.com/), China.
