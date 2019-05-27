---
layout: archive
title: "学生作品集"
date: 2017-12-30T11:40:45-04:00
modified:
excerpt: "展示学生作品集，好的丶可改进的及有趣的"
tags: []
image: 
  feature: 
  teaser: Portfolio.svg
---

<style>
h4{background: #EA1D2D; color:white; border-radius:6px; padding:6px;}
h5{background: #D19F2A; color:white; border-radius:3px; padding:3px;}
</style>
<h4>中国虚拟现实发展：广东、上海居冠；问高德地图好些</h4>
『中国哪里有虚拟现实？』『中国哪里有增强现实？』问高德地图及百度地图看中国虚拟现实及增强现实的发展。

此研究根据读取高德及百度地图“兴趣点” 或 “重要地标” POI（point of interest）搜索结果约一千笔数据。

<div class="row">
<div class="col-sm-7" markdown="1"><!-- left -->
##### POI结果省市比较：广东省总数居冠
单就省及直辖市为比较单位，广东省居冠，符合其互联网人口大省。

![省市比较]({{ "/images/VR_top10p.jpg" | absolute_url }})

##### POI结果城市比较：上海市居冠

- 单就城市为比较单位，上海市居冠，广东省内分成主要的深圳及广州。
- 上海市引领最大两类别：体育休闲及购物服务。
- 广东省深圳的公司企业多，展示深圳的私部门在此领域创新的重要地位

![城市比较]({{ "/images/VR_top10city.jpg" | absolute_url }})

</div> 
<div class="col-sm-5" markdown="1" ><!-- right -->
##### POI结果：高德为百度两倍

- 高德地图：<i class="fa fa-map-marker" aria-hidden="true"></i><i class="fa fa-map-marker" aria-hidden="true"></i> 799笔
- 百度地图：<i class="fa fa-map-marker" aria-hidden="true"></i> 388笔

##### POI分布：珠江三角洲
![高德地图数据-珠江三角洲]({{ "/images/VR_map_Pearl_Delta.jpg" | absolute_url }})

* 就珠江三角洲地区来看，数量最多的体育休闲服务分布最广。
* 公司企业集中在深圳；生活服务多在广州，东莞两类各一点。
* 政府机构及社会团体方面，就一点在广州。

</div>


<hr>
<br/>
以下展示其他学生作品集，好的丶可改进的及有趣的

<div class="tiles">
{% for post in site.categories.SDG %}
  {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles 把所有categories 有 SDG 的列出来-->