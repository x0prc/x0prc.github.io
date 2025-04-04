---
layout: default
title: Portfolio
---

{% include nav.html %}

<div class="bento-grid">
  {% for category in site.data.grid.categories %}
  <div class="category-card" style="border-left: 5px solid {{ category.color }}">
    <h2>{{ category.icon }} {{ category.title }}</h2>

    {% if category.collection %}
      {% assign items = site[category.collection] | sort: 'date' | reverse %}
      {% for item in items limit:3 %}
      <div class="entry">
        <h3>{{ item.title }}</h3>
        <div class="meta">
          {% if item.company %}{{ item.company }} •{% endif %}
          {% if item.duration %}{{ item.duration }}{% else %}{{ item.date | date: "%Y" }}{% endif %}
        </div>
        {{ item.excerpt }}
      </div>
      {% endfor %}
      <a href="/{{ category.collection }}" class="see-more">View all {{ category.collection }} →</a>

    {% elsif category.items %}
      <ul>
        {% for item in category.items %}
        <li>{{ item }}</li>
        {% endfor %}
      </ul>
    {% endif %}
  </div>
  {% endfor %}
</div>
