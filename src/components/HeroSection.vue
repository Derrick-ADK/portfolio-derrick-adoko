<script setup>
import {
  Github,
  Linkedin,
  ArrowUpRight,
  Download,
  Code2
} from 'lucide-vue-next'
</script>

<template>
  <section id="home" class="hero-section">

    <div class="hero-container">

      <div class="hero-content">

        <div class="availability">
          <span class="status-dot"></span>
          Open to professional opportunities
        </div>

        <p class="hero-intro">
          Bonjour, je suis
        </p>

        <h1>
          Derrick
          <span>ADOKO.</span>
        </h1>

        <h2>
          AI & Data Enthusiast
          <br />
          <span>Software Developer.</span>
        </h2>

        <p class="hero-description">
          Je transforme les données et l'intelligence artificielle
          en solutions technologiques concrètes.

          Passionné par la Data Science, le Machine Learning
          et le développement d'applications web innovantes.
        </p>

        <div class="hero-actions">

          <a href="#projects" class="btn-primary">
            Découvrir mes projets
            <ArrowUpRight :size="18" />
          </a>

          <a
            href="/CV_Derrick_ADOKO.pdf"
            download ="CV_Derrick_ADOKO.pdf"
            class="btn-secondary"
          >
            Télécharger mon CV
            <Download :size="18" />
          </a>

        </div>

        <div class="social-links">

          <a
            href="https://github.com/Derrick-ADK"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="GitHub"
          >
            <Github />
          </a>

          <a
            href="https://www.linkedin.com/in/derrick-adoko/"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="LinkedIn"
          >
            <Linkedin />
          </a>

          <span class="social-separator"></span>

          <span>Basé au Bénin 🇧🇯</span>

        </div>

      </div>

     <div class="hero-visual">
  <div class="visual-glow"></div>

  <div class="profile-image-wrapper">
    <img
      src="/images/Moimeme.png"
      alt="Portrait professionnel de Derrick ADOKO"
      class="profile-image"
      width="420"
      height="520"
      fetchpriority="high"
    />

    <div class="profile-image-caption">
      <span class="status-dot"></span>
      AI & Data Developer
    </div>
  </div>

  <div class="floating-tag tag-one">Python</div>
  <div class="floating-tag tag-two">Vue.js</div>
  <div class="floating-tag tag-three">Machine Learning</div>
</div>

    </div>

    <a href="#about" class="scroll-indicator">
      SCROLL TO EXPLORE ↓
    </a>

  </section>
</template>