---
layout: page
title: All articles are here
titlebar: archives
subtitle: <span class="mega-octicon octicon-calendar"></span>&nbsp;&nbsp;专题系列： &nbsp;&nbsp; <a href ="http://www.mart1n.cn/arch.html">架构</a>&nbsp;&nbsp; <a href ="http://www.mart1n.cn/life.html">故事</a>&nbsp;&nbsp; <a href ="http://www.mart1n.cn/jvm.html">JVM</a>&nbsp;&nbsp; <a href ="http://www.mart1n.cn/spring.html">Spring</a>
menu: archives
css: ['blog-page.css']
permalink: /archives.html
---

<ul class="archives-list">
  {% for post in site.posts %}

    {% unless post.next %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h3>{{ post.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}

    <li><span>{{ post.date | date:'%m-%d' }}</span> <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
