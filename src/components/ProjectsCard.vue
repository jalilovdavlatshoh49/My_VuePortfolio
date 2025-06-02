<template>
  <section class="card">
    <h2>Проекты на GitHub</h2>
    <div class="projects">
      <div v-for="project in profile.projects" :key="project.title" class="project">
        <a :href="project.link" target="_blank" class="project-title">{{ project.title }}</a>
        <p class="project-desc">{{ project.description }}</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import profile from '../data/profile.json'
</script>
