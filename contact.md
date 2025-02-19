---
layout: default
title: Contact - Ronald Mego
---

<div class="professional-banner smaller">
  <div class="banner-content">
    <h1>Let's Connect</h1>
    <p class="tagline">Disponible para consultoría, colaboraciones y oportunidades profesionales</p>
  </div>
</div>

<div class="contact-grid">
  <a href="https://www.linkedin.com/in/ronaldmego/" class="contact-card linkedin" target="_blank">
    <i class="fab fa-linkedin"></i>
    <h3>LinkedIn</h3>
    <p>Mantengamos conexión profesional y networking</p>
  </a>

  <a href="https://github.com/ronaldmego" class="contact-card github" target="_blank">
    <i class="fab fa-github"></i>
    <h3>GitHub</h3>
    <p>Explora mis proyectos y repositorios de código</p>
  </a>
  
  <a href="https://www.tiktok.com/@ronald_mego" class="contact-card tiktok" target="_blank">
    <i class="fab fa-tiktok"></i>
    <h3>TikTok</h3>
    <p>Tips rápidos y tutoriales sobre Data Analytics</p>
  </a>

  <a href="https://x.com/MGOData" class="contact-card twitter" target="_blank">
    <i class="fab fa-twitter"></i>
    <h3>Twitter</h3>
    <p>Análisis y debates sobre tendencias en datos</p>
  </a>
  
  <a href="https://www.instagram.com/megodata" class="contact-card instagram" target="_blank">
    <i class="fab fa-instagram"></i>
    <h3>Instagram</h3>
    <p>Contenido visual sobre mi día a día profesional</p>
  </a>
  
  <a href="https://www.youtube.com/@aprendamosai" class="contact-card youtube" target="_blank">
    <i class="fab fa-youtube"></i>
    <h3>YouTube</h3>
    <p>Tutoriales detallados y contenido educativo</p>
  </a>

  <a href="https://linktr.ee/ronaldmego" class="contact-card linktree" target="_blank">
    <i class="fas fa-link"></i>
    <h3>Linktree</h3>
    <p>Accede a todos mis enlaces desde un solo lugar</p>
  </a>
</div>

<div class="contact-email">
  <h2>Contacto Directo</h2>
  <a href="mailto:ronald.mego@outlook.com" class="email-link">
    <i class="fas fa-envelope"></i>
    ronald.mego@outlook.com
  </a>
  <p class="email-note">Para consultas de negocios, colaboraciones o propuestas</p>
</div>

<div class="form-section">
  <div class="container">
    <h2 class="form-title">Envíame un mensaje</h2>
    <p class="form-subtitle">Cuéntame sobre tu proyecto o consulta</p>
    
    <form class="contact-form" id="contact-form" action="https://formspree.io/f/xbldqwpb" method="POST">
      <div class="form-row">
        <div class="form-group">
          <label for="name">Nombre</label>
          <input type="text" id="name" name="name" required>
        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" id="email" name="email" required>
        </div>
      </div>
      
      <div class="form-group">
        <label for="subject">Asunto</label>
        <input type="text" id="subject" name="subject" required>
      </div>
      
      <div class="form-group">
        <label for="message">Mensaje</label>
        <textarea id="message" name="message" rows="6" required></textarea>
      </div>
      
      <div class="form-group">
        <label class="checkbox-container">
          <input type="checkbox" required>
          <span class="checkmark"></span>
          Acepto la <a href="#">política de privacidad</a>
        </label>
      </div>
      
      <!-- Campos ocultos para Formspree - colocar AQUÍ, justo antes del botón -->
      <input type="hidden" name="_next" value="https://ronaldmego.github.io/contact?submitted=true">
      <input type="hidden" name="_captcha" value="false">
      <input type="hidden" name="_subject" value="Nuevo mensaje desde ronaldmego.github.io">
      
      <button type="submit" class="submit-button">
        Enviar mensaje <i class="fas fa-paper-plane"></i>
      </button>
    </form>
  </div>
</div>

<div class="contact-cta faq-cta">
  <div class="cta-content">
    <h2>¿Buscas servicios de consultoría en Data Analytics?</h2>
    <a href="/portfolio" class="cta-button">Explora mi portfolio <i class="fas fa-arrow-right"></i></a>
  </div>
</div>

<script>
  document.addEventListener('DOMContentLoaded', function() {
    const contactForm = document.getElementById('contact-form');
    const originalContent = contactForm.innerHTML;
    
    contactForm.addEventListener('submit', function(e) {
      const submitButton = this.querySelector('.submit-button');
      submitButton.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Enviando...';
      submitButton.disabled = true;
      
      // El formulario se enviará normalmente a Formspree
      // No necesitamos prevenir el comportamiento predeterminado
    });
    
    // Verificar si el usuario viene de vuelta después de enviar el formulario
    const urlParams = new URLSearchParams(window.location.search);
    if (urlParams.get('submitted') === 'true') {
      contactForm.innerHTML = `
        <div class="success-message">
          <i class="fas fa-check-circle"></i>
          <h3>¡Mensaje enviado con éxito!</h3>
          <p>Gracias por contactarme. Te responderé a la brevedad posible.</p>
        </div>
      `;
    }
  });
</script>