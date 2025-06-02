<template>
  <nav class="navbar" :class="{ dark: darkMode }">
    <div class="logo">DJ</div>
    <button class="hamburger" :class="{ open: open }" @click="open = !open" aria-label="Menu">
      <span />
      <span />
      <span />
    </button>
    <div class="nav-links" :class="{ show: open }">
      <a href="#about" @click="open = false">Дар бораи ман</a>
      <a href="#projects" @click="open = false">Лоиҳаҳо</a>
      <a href="#contact" @click="open = false">Алоқа</a>
      <button class="dark-toggle" @click="$emit('toggleDark')" aria-label="Toggle Theme">
        <svg v-if="darkMode" viewBox="0 0 24 24" fill="none"><path d="M12 2a1 1 0 0 1 1 1v1a1 1 0 1 1-2 0V3a1 1 0 0 1 1-1zm6.364 3.636a1 1 0 0 1 1.414 1.414l-.707.707a1 1 0 1 1-1.414-1.414l.707-.707zM21 11a1 1 0 1 1 0 2h-1a1 1 0 1 1 0-2h1zm-2.636 7.364a1 1 0 1 1-1.414 1.414l-.707-.707a1 1 0 1 1 1.414-1.414l.707.707zM12 21a1 1 0 0 1-1-1v-1a1 1 0 1 1 2 0v1a1 1 0 0 1-1 1zm-7.364-2.636a1 1 0 1 1-1.414-1.414l.707-.707a1 1 0 1 1 1.414 1.414l-.707.707zM3 13a1 1 0 1 1 0-2h1a1 1 0 1 1 0 2H3zm2.636-7.364a1 1 0 1 1 1.414-1.414l.707.707A1 1 0 1 1 6.05 6.757l-.707-.707z" fill="currentColor"/><circle cx="12" cy="12" r="5" fill="currentColor"/></svg>
        <svg v-else viewBox="0 0 24 24" fill="none"><path d="M21 12.79A9 9 0 0 1 12.79 3a1 1 0 0 0-1.221 1.221A7 7 0 1 0 20.779 14.01A1 1 0 0 0 21 12.79z" fill="currentColor"/></svg>
      </button>
    </div>
    <div class="overlay" v-if="open" @click="open = false"></div>
  </nav>
</template>
<script setup>
import { ref } from 'vue'
defineProps(['darkMode'])
const open = ref(false)
</script>