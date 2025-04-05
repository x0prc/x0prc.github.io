---
layout: default
title: Portfolio
---

{% for category in site.data.categories.categories %}
<section id="{{ category.title | downcase }}">
<div class="category-card" style="border-left-color: {{ category.color }};">
<h2>{{ category.title }}</h2>

{% for item in category.items %}
<div class="tile">
{% if item.title %}
<h3>{{ item.title }}</h3>
{% endif %}

{% if item.description %}
<p>{{ item.description }}</p>
{% endif %}

{% if item.tech %}
<p><strong>Tech:</strong> {{ item.tech }}</p>
{% endif %}

{% if item.impact %}
<p><strong>Impact:</strong> {{ item.impact }}</p>
{% endif %}

{% if item.company %}
<p><strong>Company:</strong> {{ item.company }}</p>
<p><strong>Duration:</strong> {{ item.duration }}</p>
<ul>
{% for achievement in item.achievements %}
<li>{{ achievement }}</li>
{% endfor %}
</ul>
{% endif %}

{% if item.degree %}
<p><strong>Degree:</strong> {{ item.degree }}</p>
<p><strong>University:</strong> {{ item.university }}</p>
<p><strong>Year:</strong> {{ item.year }}</p>
{% endif %}

{% if category.title == "Interests" %}
<ul>
{% for interest in category.items %}
<li>{{ interest }}</li>
{% endfor %}
</ul>
{% endif %}
</div>
{% endfor %}
</div>
</section>
{% endfor %}
