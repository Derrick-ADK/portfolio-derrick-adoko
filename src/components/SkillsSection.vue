<script setup>
import { skillGroups } from '../data/skills'
import { Code2 } from 'lucide-vue-next'
</script>

<template>
  <section id="skills" class="section section-alt">

    <div class="section-container">

      <div class="section-heading">
        <span class="section-label">02 — COMPÉTENCES</span>

        <h2>
          Mon arsenal
          <span>technologique.</span>
        </h2>

        <p>
          Des technologies et outils que j'utilise pour concevoir,
          développer et expérimenter des solutions numériques.
        </p>
      </div>

      <div class="skills-grid">

        <article
          v-for="group in skillGroups"
          :key="group.title"
          class="skill-card"
        >

          <Code2 :size="30" />

          <h3>{{ group.title }}</h3>

          <p>{{ group.description }}</p>

          <div class="skill-tags">

            <span
              v-for="skill in group.skills"
              :key="skill"
            >
              {{ skill }}
            </span>

          </div>

        </article>

      </div>

    </div>

  </section>
</template>