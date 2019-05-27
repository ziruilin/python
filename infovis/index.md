---
layout: archive
title: "信息可视化作品集"
date: 2018-1-1T14:25:45-04:00
modified:
excerpt: ""
tags: []
image: 
  feature: 
  teaser:
---

- <a href="https://public.tableau.com/views/1_5302/1_1?:embed=y&:display_count=yes&publish=yes" target="_blank">![仪表板 1.png](https://i.loli.net/2018/01/08/5a52b3382378c.png)</a>

其他作品
<div class="tiles">
{% for post in site.categories.visualization %}
  {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles 把所有categories 有 visualization 的列出来-->