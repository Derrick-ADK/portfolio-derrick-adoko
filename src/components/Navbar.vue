<script setup>
import { ref } from 'vue'
import { Menu, X } from 'lucide-vue-next'

const isOpen = ref(false)

const links = [
  { name: 'Accueil', href: '#home' },
  { name: 'À propos', href: '#about' },
  { name: 'Compétences', href: '#skills' },
  { name: 'Projets', href: '#projects' },
  { name: 'Expériences', href: '#experience' },
]

const closeMenu = () => {
  isOpen.value = false
}
</script>

<template>
  <header class="navbar">
    <nav class="nav-container">

      <a href="#home" class="logo" @click="closeMenu">
        D<span>.</span>ADOKO
      </a>

      <div class="nav-links" :class="{ active: isOpen }">

        <a
          v-for="link in links"
          :key="link.name"
          :href="link.href"
          @click="closeMenu"
        >
          {{ link.name }}
        </a>

        <a
          href="#contact"
          class="nav-contact"
          @click="closeMenu"
        >
          Me contacter
        </a>

      </div>

      <button
        class="menu-button"
        @click="isOpen = !isOpen"
        aria-label="Ouvrir le menu"
        :aria-expanded="isOpen"
      >
        <X v-if="isOpen" />
        <Menu v-else />
      </button>

    </nav>
  </header>
</template>