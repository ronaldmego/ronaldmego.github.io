---
layout: default
title: Blog - Ronald Mego
---

<div class="professional-banner smaller">
  <div class="banner-content">
    <h1>Blog</h1>
    <p class="tagline">Compartiendo conocimiento en Data Analytics, AI y tendencias tecnológicas</p>
  </div>
</div>

<div class="blog-filters">
  <div class="container">
    <div class="filter-buttons">
      <button class="filter-btn active" data-filter="all">Todos los temas</button>
      <button class="filter-btn" data-filter="ai">Inteligencia Artificial</button>
      <button class="filter-btn" data-filter="data-analytics">Data Analytics</button>
      <button class="filter-btn" data-filter="career">Desarrollo Profesional</button>
    </div>
    <div class="search-container">
      <input type="text" id="blog-search" class="search-input" placeholder="Buscar artículos...">
      <i class="fas fa-search search-icon"></i>
    </div>
  </div>
</div>

<div class="posts-container">
  {% for post in site.posts %}
  <article class="post-preview" 
    {% if post.tags contains "AI" or post.tags contains "Machine Learning" or post.tags contains "Artificial Intelligence" or post.tags contains "NLP" or post.tags contains "RAG" or post.tags contains "LLM" %}
      data-category="ai"
    {% elsif post.tags contains "Career Development" or post.tags contains "Industry Trends" or post.tags contains "Tech Education" %}
      data-category="career"
    {% else %}
      data-category="data-analytics"
    {% endif %}
    data-title="{{ post.title | downcase }}"
    data-tags="{{ post.tags | join: ' ' | downcase }}"
  >
    <div class="post-cover">
      {% if post.cover_image %}
        <img src="{{ post.cover_image }}" alt="{{ post.title }}" loading="lazy">
      {% endif %}
    </div>
    <div class="post-content-preview">
      <div class="post-meta">
        <span class="post-date">
          <i class="far fa-calendar-alt"></i>
          {{ post.date | date: "%d %B, %Y" }}
        </span>
        {% if post.reading_time %}
          <span class="reading-time">
            <i class="far fa-clock"></i>
            {{ post.reading_time }} min de lectura
          </span>
        {% endif %}
      </div>
      
      <h2 class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></h2>
      
      <p class="preview-text">{{ post.excerpt | strip_html | truncatewords: 35 }}</p>
      
      {% if post.tags %}
      <div class="post-tags">
        {% for tag in post.tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>
      {% endif %}
      
      <a href="{{ post.url }}" class="read-more-link">
        Leer artículo completo <i class="fas fa-long-arrow-alt-right"></i>
      </a>
    </div>
  </article>
  {% endfor %}
</div>

<div class="pagination">
  <div class="pagination-links">
    <a href="#" class="pagination-link disabled"><i class="fas fa-chevron-left"></i> Anterior</a>
    <a href="#" class="pagination-link active">1</a>
    <a href="#" class="pagination-link disabled">Siguiente <i class="fas fa-chevron-right"></i></a>
  </div>
</div>

{% if site.posts.size == 0 %}
<div class="section-message">
  <i class="fas fa-pen-fancy"></i>
  <h3>Blog en Construcción</h3>
  <p>Estoy preparando contenido valioso sobre Data Analytics, AI y experiencias profesionales. ¡Vuelve pronto!</p>
</div>
{% endif %}

<div class="newsletter-signup">
  <div class="container">
    <div class="newsletter-content">
      <div class="newsletter-info">
        <h2>Suscríbete al newsletter</h2>
        <p>Recibe actualizaciones sobre nuevos artículos, recursos y tendencias en el mundo de los datos.</p>
      </div>
      <form class="newsletter-form">
        <div class="form-group">
          <input type="email" placeholder="Tu correo electrónico" required class="form-input">
          <button type="submit" class="form-button">Suscribirse</button>
        </div>
        <div class="form-disclaimer">
          <small>Tu privacidad es importante. Nunca compartimos tu información.</small>
        </div>
      </form>
    </div>
  </div>
</div>

<script>
  document.addEventListener('DOMContentLoaded', function() {
    // Filtrado por categorías
    const filterButtons = document.querySelectorAll('.filter-btn');
    const postPreviews = document.querySelectorAll('.post-preview');
    const searchInput = document.getElementById('blog-search');
    
    function filterPosts() {
      const searchTerm = searchInput.value.toLowerCase().trim();
      const activeFilter = document.querySelector('.filter-btn.active').dataset.filter;
      
      postPreviews.forEach(post => {
        const postTitle = post.dataset.title;
        const postTags = post.dataset.tags;
        const postCategory = post.dataset.category;
        
        const matchesSearch = searchTerm === '' || 
                             postTitle.includes(searchTerm) || 
                             postTags.includes(searchTerm);
                             
        const matchesCategory = activeFilter === 'all' || postCategory === activeFilter;
        
        if (matchesSearch && matchesCategory) {
          post.style.display = 'flex';
          setTimeout(() => {
            post.classList.add('fade-in');
          }, 100);
        } else {
          post.style.display = 'none';
          post.classList.remove('fade-in');
        }
      });
    }
    
    filterButtons.forEach(button => {
      button.addEventListener('click', function() {
        filterButtons.forEach(btn => btn.classList.remove('active'));
        this.classList.add('active');
        filterPosts();
      });
    });
    
    searchInput.addEventListener('input', filterPosts);
  });
</script>