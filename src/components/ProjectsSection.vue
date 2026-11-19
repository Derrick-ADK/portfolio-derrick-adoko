<script setup>
import { projects } from '../data/projects'
import { Github, ExternalLink, ArrowUpRight } from 'lucide-vue-next'
</script>

<template>
  <section id="projects" class="section">

    <div class="section-container">

      <div class="section-heading">

        <span class="section-label">03 — RÉALISATIONS</span>

        <h2>
          Des idées transformées
          <span>en projets.</span>
        </h2>

        <p>
          Une sélection de mes travaux et expérimentations
          dans les domaines de l'IA, de la Data et du développement.
        </p>

      </div>

      <div class="projects-grid">

        <article
          v-for="project in projects"
          :key="project.number"
          class="project-card"
        >

          <div class="project-top">

            <span>{{ project.category }}</span>

            <span class="project-number">
              {{ project.number }}
            </span>

          </div>

          <h3>{{ project.title }}</h3>

          <p class="project-description">
            {{ project.description }}
          </p>

          <div class="project-details">

            <p>
              <strong>Problématique :</strong>
              {{ project.problem }}
            </p>

            <p>
              <strong>Approche :</strong>
              {{ project.solution }}
            </p>

          </div>

          <div class="skill-tags">

            <span
              v-for="tech in project.technologies"
              :key="tech"
            >
              {{ tech }}
            </span>

          </div>

          <div class="project-footer">

            <span class="project-status">
              {{ project.status }}
            </span>

            <div class="project-links">

              <a
                v-if="project.github"
                :href="project.github"
                target="_blank"
                rel="noopener noreferrer"
                aria-label="Voir le code source"
              >
                <Github :size="20" />
              </a>

              <a
                v-if="project.demo"
                :href="project.demo"
                target="_blank"
                rel="noopener noreferrer"
                aria-label="Voir la démonstration"
              >
                <ExternalLink :size="20" />
              </a>

              <ArrowUpRight v-if="!project.github && !project.demo" />

            </div>

          </div>

        </article>

      </div>

    </div>

  </section>
</template>