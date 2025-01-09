---
layout: default
title: Blog - Ronald Mego
---

<div class="blog-header">
  <h1>Blog</h1>
  <p class="subtitle">Compartiendo mi experiencia sobre Data, Analytics, y tecnología</p>
</div>

<div class="posts-container">
  {% for post in site.posts %}
  <article class="post-preview">
    <div class="post-cover">
      {% if post.cover_image %}
        <img src="{{ post.cover_image }}" alt="{{ post.title }}">
      {% endif %}
    </div>
    <div class="post-meta">
      <span class="date">{{ post.date | date: "%d %B, %Y" }}</span>
      {% if post.reading_time %}
        <span class="reading-time">Lectura: {{ post.reading_time }} min</span>
      {% endif %}
    </div>
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <p class="preview-text">{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
    {% if post.tags %}
    <div class="tags">
      {% for tag in post.tags %}
        <span class="tag">{{ tag }}</span>
      {% endfor %}
    </div>
    {% endif %}
  </article>
  {% endfor %}
</div>

{% if site.posts.size == 0 %}
<div class="section-message">
  <i class="fas fa-tools"></i>
  <h3>Blog en Construcción</h3>
  <p>Estoy preparando contenido valioso sobre Data Analytics, AI, y experiencias en el campo. ¡Vuelve pronto!</p>
</div>
{% endif %}