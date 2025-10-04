---
layout: page
title: News
permalink: /news/
---
{% if site.collections.news.docs %}
  {% for item in site.collections.news.docs %}
    <div class="news-item">
      {% if item.image %}
        <img src="{{ item.image | relative_url }}" alt="{{ item.title }}" class="news-image">
      {% endif %}
      <div class="news-content">
        <h3>{{ item.date | date: "%B %d, %Y" }} - <a href="{{ item.url | relative_url }}">{{ item.title }}</a></h3>
        {{ item.content | strip_html | truncatewords: 20 }} <a href="{{ item.url | relative_url }}">Read more</a>
      </div>
    </div>
  {% endfor %}
{% else %}
  <p>No news items available.</p>
{% endif %}