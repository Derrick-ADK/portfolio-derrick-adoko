<script setup>
import { GraduationCap, Brain, Rocket } from 'lucide-vue-next'

const qualities = [
  {
    icon: GraduationCap,
    title: 'Formation',
    description: 'Intelligence Artificielle & Data à IFRI/UAC.'
  },
  {
    icon: Brain,
    title: 'Passion',
    description: 'Intelligence artificielle, analyse de données et innovation.'
  },
  {
    icon: Rocket,
    title: 'Ambition',
    description: 'Concevoir des solutions technologiques à forte valeur ajoutée.'
  }
]
</script>

<template>
  <section id="about" class="section">

    <div class="section-container">

      <div class="section-heading">
        <span class="section-label">01 — À PROPOS</span>
        <h2>
          Derrière le code,
          <span>une vision.</span>
        </h2>
      </div>

      <div class="about-grid">

        <div class="about-description">

          <p class="about-lead">
            Je suis Derrick ADOKO, étudiant en Intelligence
            Artificielle & Data à l'IFRI, au Bénin.
          </p>

          <p>
            Passionné par les nouvelles technologies, je m'intéresse
            particulièrement à la manière dont l'intelligence
            artificielle et l'exploitation des données peuvent
            contribuer à résoudre des problématiques réelles.
          </p>

          <p>
            Mon parcours me permet de développer une double
            compétence : comprendre les problématiques liées
            aux données et concevoir des applications web
            permettant de transformer les idées en solutions concrètes.
          </p>

          <p>
            Je cherche constamment à apprendre, expérimenter
            et développer mes capacités à travers des projets
            personnels, académiques et professionnels.
          </p>

        </div>

        <div class="about-cards">

          <article
            v-for="item in qualities"
            :key="item.title"
            class="about-card"
          >

            <component :is="item.icon" :size="28" />

            <div>
              <h3>{{ item.title }}</h3>
              <p>{{ item.description }}</p>
            </div>

          </article>

        </div>

      </div>

    </div>

  </section>
</template>