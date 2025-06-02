<template>
  <section>
    <h2>Дар бораи ман</h2>
    <p>{{ data.about }}</p>
    <ul>
      <li><strong>Ном:</strong> {{ data.name }}</li>
      <li><strong>Касб:</strong> {{ data.title }}</li>
    </ul>
  </section>
</template>

<script setup>
import data from '../assets/data.json'
</script>