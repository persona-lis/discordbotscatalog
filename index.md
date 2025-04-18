---
layout: default
title: Главная
---

<div class="hero">
  <h1>Melano</h1>
  <p>Каталог лучших Discord-ботов с фильтрацией, категориями и удобным поиском.</p>
</div>

<div class="search-container">
  <input type="text" id="bot-search" placeholder="🔍 Найти бота..." oninput="searchBots()">
</div>

<h2>Популярные боты</h2>
<div class="bot-grid" id="bot-list">
  {% assign bots_sorted = site.bots | sort: "rating" | reverse %}
  {% for bot in bots_sorted limit: 9 %}
    <a href="{{ bot.url | relative_url }}" class="bot-card">
      <h3>{{ bot.title }}</h3>
      <p>{{ bot.description | truncate: 80 }}</p>
      <span class="category-tag">{{ bot.category }}</span>
    </a>
  {% endfor %}
</div>

<h2><a href="{{ '/categories/' | relative_url }}">Посмотреть все категории →</a></h2>

<script>
  function searchBots() {
    const input = document.getElementById('bot-search').value.toLowerCase();
    const cards = document.querySelectorAll('.bot-card');
    cards.forEach(card => {
      const text = card.innerText.toLowerCase();
      card.style.display = text.includes(input) ? '' : 'none';
    });
  }
</script>
