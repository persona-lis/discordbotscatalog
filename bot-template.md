{% raw %}
<!-- _includes/bot-templates.html -->

<div class="bot-card">
  <div class="bot-card-header">
    <h2 class="bot-name">{{ bot.name }}</h2>
    <span class="bot-category">{{ bot.category }}</span>
  </div>

  <p class="bot-description">{{ bot.description }}</p>

  <div class="bot-tags">
    {% if bot.tags %}
      {% for tag in bot.tags %}
        <span class="bot-tag">#{{ tag }}</span>
      {% endfor %}
    {% endif %}
  </div>

  <div class="bot-links">
    {% if bot.invite %}
      <a href="{{ bot.invite }}" class="bot-button" target="_blank">➕ Пригласить</a>
    {% endif %}
    {% if bot.website %}
      <a href="{{ bot.website }}" class="bot-button secondary" target="_blank">🌐 Сайт</a>
    {% endif %}
    {% if bot.support %}
      <a href="{{ bot.support }}" class="bot-button secondary" target="_blank">💬 Поддержка</a>
    {% endif %}
  </div>
</div>
{% endraw %}
