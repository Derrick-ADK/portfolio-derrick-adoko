<script setup>
import { BriefcaseBusiness, GraduationCap } from 'lucide-vue-next'

const experiences = [
  {
    type: 'experience',
    title: 'Stagiaire',
    organization: 'Euphorbia Group',
    period: 'Août 2025 – Novembre 2025',
    description:
      'Découverte de solutions de Business Intelligence, expérimentation de Metabase et exploration des outils et environnements informatiques.'
  },
  {
    type: 'experience',
    title: 'Stagiaire',
    organization: 'Cabinet SUTISUA (Cabinet d\'expertise comptable )',
    period: 'Mars 2026 – Juin 2025',
    description:
      'Participation aux activités techniques et au traitement de données. Découverte des problématiques de gestion et d’exploitation des données en entreprise.'
  }
]

const education = [
    {
    title: 'Mathématiques Informatique Appliquée',
    organization: 'FAST – Université d’Abomey-Calavi',
    period: '2021 - 2023',
    description:
      'Formation en Mathématique, physique et informatique appliquée.'
  },
  {
    title: 'Licence en Intelligence Artificielle & Data',
    organization: 'IFRI – Université d’Abomey-Calavi',
    period: 'En cours',
    description:
      'Formation en informatique, programmation, intelligence artificielle, analyse de données et apprentissage automatique.'
  }
]
</script>

<template>
  <section id="experience" class="section section-alt">

    <div class="section-container">

      <div class="section-heading">
        <span class="section-label">04 — PARCOURS</span>

        <h2>
          Mon parcours
          <span>académique & professionnel.</span>
        </h2>
      </div>

      <div class="timeline-grid">

        <div>

          <h3 class="timeline-heading">
            <BriefcaseBusiness />
            Expériences
          </h3>

          <article
            v-for="item in experiences"
            :key="item.organization"
            class="timeline-card"
          >

            <span class="timeline-date">
              {{ item.period }}
            </span>

            <h4>{{ item.title }}</h4>

            <h5>{{ item.organization }}</h5>

            <p>{{ item.description }}</p>

          </article>

        </div>

        <div>

          <h3 class="timeline-heading">
            <GraduationCap />
            Formation
          </h3>

          <article
            v-for="item in education"
            :key="item.organization"
            class="timeline-card"
          >

            <span class="timeline-date">
              {{ item.period }}
            </span>

            <h4>{{ item.title }}</h4>

            <h5>{{ item.organization }}</h5>

            <p>{{ item.description }}</p>

          </article>

        </div>

      </div>

    </div>

  </section>
</template>