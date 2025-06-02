<template>
  <section class="card github-projects">
    <h2 class="section-title">Проекты на GitHub</h2>
    <div class="projects">
      <div v-for="project in profile.projects" :key="project.title" class="project">
        <a :href="project.link" target="_blank" class="project-title">
          {{ project.title }}
        </a>
        <p v-if="project.description" class="project-desc">
          {{ project.description }}
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import profile from '../data/profile.json'
</script>

<style scoped>
.github-projects {
  width: 100%;
  max-width: 720px;
  margin: 0 auto;
  padding: 20px 16px;
  box-sizing: border-box;
  font-family: 'Inter', sans-serif;
  color: var(--text-color);
}

.section-title {
  font-size: 1.3rem;
  font-weight: 600;
  margin-bottom: 18px;
  color: var(--text-color);
}

.projects {
  display: flex;
  flex-direction: column;
  gap: 20px; /* Масофа байни проектҳо */
}

.project {
  padding: 16px;
  background-color: var(--chip-bg);
  border-radius: 14px;
  box-shadow: 0 4px 18px rgba(80, 120, 200, 0.15);
  transition: background-color 0.3s ease, box-shadow 0.3s ease;
}

.project:hover {
  background-color: var(--accent-color);
  color: white;
}

.project-title {
  font-size: 1.05rem;
  font-weight: 600;
  color: inherit;
  text-decoration: none;
}

.project-title:hover {
  text-decoration: underline;
}

.project-desc {
  font-size: 0.95rem;
  margin-top: 6px;
  color: var(--secondary-color);
}

/* Адаптив барои мобил */
@media (max-width: 600px) {
  .section-title {
    font-size: 1.15rem;
  }

  .project-title {
    font-size: 1rem;
  }

  .project-desc {
    font-size: 0.9rem;
  }

  .project {
    padding: 14px;
  }
}
</style>
