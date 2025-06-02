<template>
  <section class="card">
    <h2>Языки программирования</h2>
    <ul class="chips">
      <li v-for="lang in profile.languages" :key="lang">{{ lang }}</li>
    </ul>
    <h2>Фреймворки и технологии</h2>
    <ul class="chips">
      <li v-for="fw in profile.frameworks" :key="fw">{{ fw }}</li>
    </ul>
  </section>
</template>

<script setup>
import profile from '../data/profile.json'
</script>
