<template>
  <div class="wrapper">
    <Transition name="fade-slide" appear>
      <div class="card-container">
        <ProfileCard />
      </div>
    </Transition>

    <Divider />

    <Transition name="fade-slide" appear>
      <div class="card-container">
        <KnowledgeCard />
      </div>
    </Transition>

    <Divider />

    <Transition name="fade-slide" appear>
      <div class="card-container">
        <ProjectsCard />
      </div>
    </Transition>
  </div>
</template>

<script setup>
import ProfileCard from './components/ProfileCard.vue'
import KnowledgeCard from './components/KnowledgeCard.vue'
import ProjectsCard from './components/ProjectsCard.vue'
import Divider from './components/Divider.vue'
</script>

<style scoped>
.wrapper {
  max-width: 960px;
  margin: 0 auto;
  padding: 2rem 1rem;
  background-color: var(--bg-color);
  color: var(--text-color);
  font-family: var(--font-family);
  transition: background-color 0.3s ease, color 0.3s ease;
}

.card-container {
  background-color: var(--card-color);
  border-radius: var(--border-radius);
  box-shadow: 0 6px 24px var(--card-shadow);
  padding: 1.7rem 1.5rem;
  margin-bottom: 2rem;
  transition: box-shadow 0.3s ease, background-color 0.3s ease;
}

.card-container:hover {
  box-shadow: 0 10px 32px var(--card-shadow);
}

:deep(.divider) {
  height: 1px;
  margin: 24px 0;
  background: linear-gradient(to right, transparent, var(--accent-color), transparent);
}

/* Аниматсия (transition) */
.fade-slide-enter-active {
  transition: all 0.5s ease;
}
.fade-slide-leave-active {
  transition: all 0.3s ease;
}
.fade-slide-enter-from {
  opacity: 0;
  transform: translateY(20px);
}
.fade-slide-enter-to {
  opacity: 1;
  transform: translateY(0);
}

/* Адаптив */
@media (max-width: 768px) {
  .wrapper {
    padding: 1.5rem 1rem;
  }

  .card-container {
    padding: 1.5rem 1.2rem;
  }
}

@media (max-width: 480px) {
  .card-container {
    padding: 1.2rem 1rem;
    border-radius: 14px;
  }
}
</style>
