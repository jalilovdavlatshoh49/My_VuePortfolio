<template>
  <div class="wrapper">
    <!-- Блок профиля -->
    <ProfileCard />
    <Divider />

    <!-- Блок знаний -->
    <KnowledgeCard />
    <Divider />

    <!-- Блок проектов -->
    <ProjectsCard />
  </div>
</template>

<script setup>
// Импортируем компоненты
import ProfileCard from './components/ProfileCard.vue'
import KnowledgeCard from './components/KnowledgeCard.vue'
import ProjectsCard from './components/ProjectsCard.vue'
import Divider from './components/Divider.vue'
</script>
