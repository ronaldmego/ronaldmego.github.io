---
layout: default
title: Portfolio - Ronald Mego
---

<div class="professional-banner smaller">
  <div class="banner-content">
    <h1>Portfolio de Ronald Mego</h1>
    <p class="tagline">Proyectos destacados en Data Analytics, Machine Learning y AI</p>
  </div>
</div>

<div class="portfolio-filters">
  <div class="container">
    <div class="filter-buttons">
      <button class="filter-btn active" data-filter="all">Todos</button>
      <button class="filter-btn" data-filter="ai">Inteligencia Artificial</button>
      <button class="filter-btn" data-filter="data-analytics">Data Analytics</button>
      <button class="filter-btn" data-filter="automation">Automatización</button>
    </div>
  </div>
</div>

<div class="projects-container">
  <div class="projects-grid">
    {% for project in site.projects %}
    <article class="project-card" 
      {% if project.technologies contains "OpenAI" or project.technologies contains "LangChain" or project.technologies contains "RAG" or project.technologies contains "Phi4" or project.technologies contains "Ollama" %}
        data-category="ai"
      {% elsif project.technologies contains "GitHub Actions" or project.technologies contains "Quarto" %}
        data-category="automation"
      {% else %}
        data-category="data-analytics"
      {% endif %}
    >
      <a href="{{ project.url }}" class="project-link">
        <div class="project-image">
          {% if project.cover_image %}
            <img src="{{ project.cover_image }}" alt="{{ project.title }}" loading="lazy">
          {% endif %}
          {% if project.status == "completed" %}
            <span class="status-badge completed">Completado</span>
          {% elsif project.status == "in-progress" %}
            <span class="status-badge in-progress">En Progreso</span>
          {% else %}
            <span class="status-badge planned">Planificado</span>
          {% endif %}
        </div>
        <div class="project-content">
          <h2>{{ project.title }}</h2>
          <p class="project-description">{{ project.description }}</p>
          <div class="project-meta">
            <div class="technologies">
              {% for tech in project.technologies %}
                <span class="tech-tag">{{ tech }}</span>
              {% endfor %}
            </div>
            <div class="project-date">
              <i class="far fa-calendar-alt"></i> {{ project.date | date: "%B %Y" }}
            </div>
            <div class="project-links">
              {% if project.github_link %}
                <a href="{{ project.github_link }}" target="_blank" class="project-link-btn github">
                  <i class="fab fa-github"></i> <span class="link-text">GitHub</span>
                </a>
              {% endif %}
              {% if project.demo_link %}
                <a href="{{ project.demo_link }}" target="_blank" class="project-link-btn demo">
                  <i class="fas fa-external-link-alt"></i> <span class="link-text">Demo</span>
                </a>
              {% endif %}
            </div>
          </div>
        </div>
      </a>
    </article>
    {% endfor %}
  </div>
</div>

{% if site.projects.size == 0 %}
<div class="section-message">
  <i class="fas fa-tools"></i>
  <h3>Portfolio en Construcción</h3>
  <p>Estoy preparando proyectos interesantes para compartir. ¡Vuelve pronto!</p>
</div>
{% endif %}

<div class="contact-cta">
  <div class="cta-content">
    <h2>¿Interesado en colaborar en un proyecto?</h2>
    <a href="/contact" class="cta-button">Conversemos <i class="fas fa-arrow-right"></i></a>
  </div>
</div>

<script>
  document.addEventListener('DOMContentLoaded', function() {
    const filterButtons = document.querySelectorAll('.filter-btn');
    const projectCards = document.querySelectorAll('.project-card');

    filterButtons.forEach(button => {
      button.addEventListener('click', function() {
        // Remove active class from all buttons
        filterButtons.forEach(btn => btn.classList.remove('active'));
        
        // Add active class to clicked button
        this.classList.add('active');
        
        const filter = this.dataset.filter;
        
        projectCards.forEach(card => {
          if (filter === 'all' || card.dataset.category === filter) {
            card.style.display = 'block';
            // Add animation class
            setTimeout(() => {
              card.classList.add('fade-in');
            }, 100);
          } else {
            card.style.display = 'none';
            card.classList.remove('fade-in');
          }
        });
      });
    });
  });
</script>