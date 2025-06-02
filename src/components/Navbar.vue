<template>
  <nav class="navbar">
    <router-link to="/" exact>Асосӣ</router-link>
    <router-link to="/about">Дар бораи ман</router-link>
    <router-link to="/skills">Маҳоратҳо</router-link>
    <router-link to="/projects">Лоиҳаҳо</router-link>
    <router-link to="/contact">Тамос</router-link>
    <span class="spacer"></span>
    <button class="theme-toggle" @click="toggleTheme" :aria-label="darkMode ? 'Режими рӯшноӣ' : 'Режими торик'">
      <i :class="darkMode ? 'ph ph-sun' : 'ph ph-moon'"></i>
    </button>
  </nav>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const darkMode = ref(false)

function toggleTheme() {
  darkMode.value = !darkMode.value
  document.body.classList.toggle('dark', darkMode.value)
  localStorage.setItem('theme', darkMode.value ? 'dark' : 'light')
}

onMounted(() => {
  darkMode.value = localStorage.getItem('theme') === 'dark'
  document.body.classList.toggle('dark', darkMode.value)
})
</script>