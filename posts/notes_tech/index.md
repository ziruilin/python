---
layout: archive
title: "notes_tech"
date: 2017-12-30T11:40:45-04:00
modified:
excerpt: ""
tags: []
image: 
---


<div class="tiles">
{% for post in site.categories.notes_tech %}
  {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles 把所有categories 有 portfolio 的列出來-->