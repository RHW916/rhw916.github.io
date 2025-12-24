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
  <a href="/assets/CV_CN.pdf" target="_blank" class="cv-link">中文版 →</a>
  <a href="/assets/CV_EN.pdf" target="_blank" class="cv-link">English →</a>
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

# 📝 Blogs

在这里分享我的研究心得、学习笔记和项目经验。

## 🔬 最新博客文章

{% for post in site.posts limit:3 %}
<div class='paper-box'>
<div class='paper-box-text' markdown="1">

### [{{ post.title }}]({{ post.url | relative_url }})
<small>**{{ site.author.name }}** | {{ post.date | date: "%Y年%m月%d日" }} | 
{% if post.categories %}
  {% for category in post.categories %}
  <span class="badge">{{ category }}</span>
  {% endfor %}
{% endif %}
</small>

{{ post.excerpt | default: post.content | strip_html | truncatewords: 50 }}

[**阅读全文 →**]({{ post.url | relative_url }})
</div>
</div>
{% endfor %}

[查看所有博客文章 →](/blog/)

<!-- 如果没有博客文章，显示提示 -->
{% if site.posts.size == 0 %}
<div class='paper-box'>
<div class='paper-box-text'>
<p>目前还没有博客文章，敬请期待！</p>
</div>
</div>
{% endif %}

<style>
.badge {
  display: inline-block;
  padding: 0.25em 0.6em;
  font-size: 0.75em;
  font-weight: 700;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: 0.25rem;
  background-color: #3b82f6;
  margin-right: 5px;
}

.badge:last-child {
  margin-right: 0;
}

.paper-box {
  display: flex;
  margin-bottom: 2rem;
  padding: 1.5rem;
  border: 1px solid #eaeaea;
  border-radius: 8px;
  transition: all 0.3s ease;
}

.paper-box:hover {
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  transform: translateY(-2px);
}

.paper-box-text {
  flex: 1;
}

.paper-box-text h4 {
  margin-top: 0;
  margin-bottom: 0.5rem;
}

.paper-box-text small {
  color: #6b7280;
  display: block;
  margin-bottom: 1rem;
}

.paper-box-text a[href*="阅读全文"] {
  display: inline-block;
  margin-top: 1rem;
  color: #3b82f6;
  font-weight: 600;
  text-decoration: none;
}

.paper-box-text a[href*="阅读全文"]:hover {
  text-decoration: underline;
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
