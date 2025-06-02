<template>
  <section id="projects" class="projects-section">
    <h2>Лоиҳаҳо</h2>
    <div class="projects-list">
      <div class="project-card" v-for="project in projects" :key="project.title">
        <div class="project-image-wrap">
          <img :src="require(`../assets/${project.image}`)" :alt="project.title" class="project-image" />
        </div>
        <div class="project-info">
          <h3>{{ project.title }}</h3>
          <p>{{ project.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import projects from '../data/projects.json'
</script>