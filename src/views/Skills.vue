<template>
  <div>
    <h2>Маҳоратҳои ман</h2>
    <ul>
      <li v-for="skill in data.skills" :key="skill">{{ skill }}</li>
    </ul>
  </div>
</template>

<script setup>
import data from '../assets/data.json'
</script>