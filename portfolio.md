---
layout: default
title: Portfolio - Ronald Mego
---

<div class="portfolio-header">
  <h1>Portfolio</h1>
  <p class="subtitle">Proyectos destacados en Data Analytics, Machine Learning y AI</p>
</div>

<div class="projects-grid">
  {% for project in site.projects %}
  <article class="project-card">
    <a href="{{ project.url }}" class="project-link">
      <div class="project-image">
        {% if project.cover_image %}
          <img src="{{ project.cover_image }}" alt="{{ project.title }}">
        {% endif %}
      </div>
      <div class="project-content">
        <h2>{{ project.title }}</h2>
        <p class="project-description">{{ project.description }}</p>
        <div class="project-meta">
          <div class="technologies">
            {% for tech in project.technologies %}
              <span class="tech">{{ tech }}</span>
            {% endfor %}
          </div>
          <div class="links">
            {% if project.github_link %}
              <a href="{{ project.github_link }}" target="_blank"><i class="fab fa-github"></i> GitHub</a>
            {% endif %}
            {% if project.demo_link %}
              <a href="{{ project.demo_link }}" target="_blank"><i class="fas fa-external-link-alt"></i> Demo</a>
            {% endif %}
          </div>
        </div>
      </div>
    </a>
  </article>
  {% endfor %}
</div>