---
layout: default
title: 'All Categories'
permalink: /categories/
nav_order: 1
---

<h2 class="post-list-heading">All Categories</h2>

<div class="category-list">
  {% for category in site.categories %}
    <div class="category-item">
      <a href="{{ site.baseurl }}/categories/{{ category[0] | slugify }}/">
        {{ category[0] }} <span>({{ category[1].size }})</span>
      </a>
    </div>
  {% endfor %}
</div>

<style>
  .category-list {
    margin-top: 20px;
  }
  .category-item {
    margin-bottom: 15px;
  }
  .category-item a {
    font-size: 1.2rem;
    text-decoration: none;
    padding: 10px 15px;
    background-color: #f1f1f1;
    border-radius: 5px;
    display: inline-block;
  }
  .category-item a:hover {
    background-color: #ddd;
  }
  .category-item span {
    font-size: 0.9rem;
    color: #555;
  }
</style>
