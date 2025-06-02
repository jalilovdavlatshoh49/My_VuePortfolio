<template>
  <div class="project-card">
    <img v-if="project.image" :src="project.image" :alt="project.title" />
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
    <a :href="project.link" target="_blank" rel="noopener">[Нишон додан]</a>
  </div>
</template>

<script setup>
defineProps(['project'])
</script>