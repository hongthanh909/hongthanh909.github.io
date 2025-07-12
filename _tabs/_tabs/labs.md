---
title: Labs
layout: page
permalink: /labs/
icon: flask
order: 5
---

Dưới đây là các bài mô phỏng tấn công/phân tích log SOC:

{% assign lab_posts = site.posts | where_exp:"item", "item.categories contains 'SOC'" %}
<ul>
  {% for post in lab_posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a> - {{ post.date | date: "%Y-%m-%d" }}
    </li>
  {% endfor %}
</ul>
