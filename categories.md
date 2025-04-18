---
layout: default
title: Категории
permalink: /categories/
---

<h1 class="page-title">Категории ботов</h1>

<div class="category-grid">
  {% assign sorted_categories = site.data.categories | sort %}
  {% for category in sorted_categories %}
    {% assign emoji = site.data.category_emojis[category] %}
    <a href="/category/{{ category | downcase | replace: ' ', '-' }}/" class="category-card">
      <div class="emoji">{{ emoji }}</div>
      <div class="category-name">{{ category }}</div>
    </a>
  {% endfor %}
</div>
