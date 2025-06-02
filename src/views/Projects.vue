<template>
  <section>
    <h2>Лоиҳаҳои ман</h2>
    <div class="projects-list">
      <ProjectCard v-for="project in data.projects" :key="project.title" :project="project" />
    </div>
  </section>
</template>

<script setup>
import data from '../assets/data.json'
import ProjectCard from '../components/ProjectCard.vue'
</script>