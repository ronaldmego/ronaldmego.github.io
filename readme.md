# Personal Website - Ronald Mego

Este repositorio contiene mi sitio web personal, construido con Jekyll y alojado en GitHub Pages. El sitio incluye mi CV, portfolio y blog.

## 🏗️ Estructura del Proyecto

```
mygithubpage/
├── _config.yml                 # Configuración principal de Jekyll
├── _layouts                    # Templates de páginas
│   ├── default.html           # Layout base
│   └── post.html              # Layout para posts
├── _posts                      # Posts del blog
│   └── YYYY-MM-DD-titulo.md
├── _projects                   # Proyectos del portfolio
│   └── project-name.md
├── assets
│   ├── css
│   │   └── style.scss         # Estilos del sitio
│   ├── docs
│   │   ├── RonaldMego_CV.pdf
│   │   └── estructura.txt
│   └── images
│       ├── blog               # Imágenes de posts
│       │   └── YYYY-MM-DD-post-name/
│       │       ├── cover.jpg
│       │       └── other-images/
│       ├── portfolio          # Imágenes de proyectos
│       │   └── project-name/
│       │       ├── cover.jpg
│       │       └── screenshots/
│       └── favicon.png
├── blog.md                     # Página principal del blog
├── index.md                    # Página principal (CV)
└── portfolio.md                # Página principal del portfolio
```

## 🔧 Configuración

### Requisitos Previos
- Ruby
- Jekyll
- Bundler

### Instalación Local
1. Clonar el repositorio
```bash
git clone https://github.com/ronaldmego/mygithubpage.git
cd mygithubpage
```

2. Instalar dependencias
```bash
bundle install
```

3. Ejecutar el servidor local
```bash
bundle exec jekyll serve
```

## 📝 Guías de Actualización

### Actualizar el CV (index.md)

1. Abrir `index.md`
2. Las secciones están organizadas en:
   - Profile
   - Professional Experience
   - Education
   - Skills
   - Languages

Para añadir una nueva experiencia laboral:
```markdown
<div class="experience-item">
  <div class="experience-header">
    <h3>Título del Puesto</h3>
    <div class="experience-meta">
      <span class="company"><a href="URL">Empresa</a></span>
      <span class="location">Ciudad, País</span>
      <span class="period">MM/YYYY - MM/YYYY</span>
    </div>
  </div>
  <ul>
    <li>Logro/Responsabilidad 1</li>
    <li>Logro/Responsabilidad 2</li>
  </ul>
</div>
```

### Publicar un Nuevo Post

1. Crear un nuevo archivo en `_posts/YYYY-MM-DD-titulo-del-post.md`
2. Crear directorio para imágenes en `assets/images/blog/YYYY-MM-DD-titulo-del-post/`
3. Usar el siguiente formato:

```markdown
---
layout: post
title: "Título del Post"
date: YYYY-MM-DD
cover_image: /assets/images/blog/YYYY-MM-DD-titulo-del-post/cover.jpg
tags: [Tag1, Tag2]
reading_time: XX
---

Contenido del post en Markdown...
```

### Añadir un Proyecto al Portfolio

1. Crear nuevo archivo en `_projects/nombre-proyecto.md`
2. Crear directorio para imágenes en `assets/images/portfolio/nombre-proyecto/`
3. Usar el siguiente formato:

```markdown
---
layout: project
title: "Nombre del Proyecto"
description: "Descripción corta"
cover_image: /assets/images/portfolio/nombre-proyecto/cover.jpg
technologies: [Tech1, Tech2]
github_link: URL
demo_link: URL
date: YYYY-MM-DD
status: completed
---

Contenido del proyecto en Markdown...
```

## 🖼️ Manejo de Imágenes

### Directrices para Imágenes
- Usar JPG para fotografías
- Usar PNG para screenshots y diagramas
- Optimizar imágenes antes de subir
- Dimensiones recomendadas:
  - Cover images: 1200x630px
  - Screenshots: 1920x1080px máximo

### Nombres de Archivos
- Usar nombres descriptivos en minúsculas
- Separar palabras con guiones
- Ejemplos:
  - `cover.jpg`
  - `dashboard-screenshot.png`
  - `system-architecture.png`

## 🚀 Deployment

El sitio se despliega automáticamente en GitHub Pages cuando se hace push a la rama main.

1. Hacer commit de los cambios:
```bash
git add .
git commit -m "Descripción de los cambios"
```

2. Push a GitHub:
```bash
git push origin main
```

## 📋 Chequeos Pre-Deployment

Antes de hacer push, verificar:
- [ ] Imágenes optimizadas y en el directorio correcto
- [ ] Links funcionando correctamente
- [ ] Formato Markdown correcto
- [ ] Fechas actualizadas
- [ ] No hay errores en el servidor local

## 🎨 Personalización

### Modificar Estilos
Los estilos están en `assets/css/style.scss`. Variables principales:
```scss
$primary-color: #0366d6;
$text-color: #24292e;
$background-color: #ffffff;
$border-color: #e1e4e8;
```

### Configuración del Sitio
Editar `_config.yml` para cambiar:
- Título del sitio
- Descripción
- Links sociales
- Configuraciones de collections

## 📚 Referencias

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages](https://docs.github.com/en/pages)
- [Markdown Guide](https://www.markdownguide.org/)

## 🤝 Contribuciones

Aunque este es un sitio personal, las sugerencias son bienvenidas a través de issues o pull requests.