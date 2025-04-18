---
layout: default
---

<h1 class="page-title">Категория: {{ page.title }}</h1>

<div class="bot-grid">
  {% assign bots = site.bots | where: "category", page.title %}
  {% for bot in bots %}
    <a href="{{ bot.url }}" class="bot-card">
      <div class="bot-card-inner">
        <h3>{{ bot.title }}</h3>
        <p>{{ bot.short_description }}</p>
      </div>
    </a>
  {% endfor %}
</div>
