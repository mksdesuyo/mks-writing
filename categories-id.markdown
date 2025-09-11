---
layout: default
title: 'Semua Kategori'
permalink: /id/categories/
nav_order: 1
lang: id
ref: categories
---

<h1 class="page-heading">Kategori</h1>

<div class="category-list">
  {%- assign posts_in_lang = site.posts | where: "lang", "id" -%}
  {%- assign categories_in_lang = posts_in_lang | map: "categories" | join: "," | split: "," | uniq | sort -%}

  {%- for category in categories_in_lang -%}
    {%- if category != "" -%}
      <div class="category-item">
        {%- assign post_count = site.categories[category] | where: "lang", "id" | size -%}

        <a href="{{ site.baseurl }}/id/categories/{{ category | slugify }}/">
          {{ category }} <span>({{ post_count }})</span>
        </a>
      </div>
    {%- endif -%}
  {%- endfor -%}
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