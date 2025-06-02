<template>
  <div class="skills-list">
    <div class="skill-card" v-for="skill in skills" :key="skill.name">
      <i :class="skill.icon"></i>
      <span>{{ skill.name }}</span>
    </div>
  </div>
</template>

<script setup>
defineProps(['skills'])
</script>