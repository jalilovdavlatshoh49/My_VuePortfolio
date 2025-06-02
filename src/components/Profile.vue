<template>
  <section id="about" class="profile-section">
    <div class="profile-img-wrap">
      <img :src="require(`../assets/${profile.profileImage}`)" alt="profile" class="profile-img" />
    </div>
    <div class="profile-info">
      <h1>{{ profile.name }}</h1>
      <h2>{{ profile.title }}</h2>
      <p class="about">{{ profile.about }}</p>
      <h3>Скиллҳо</h3>
      <ul class="skills">
        <li v-for="skill in profile.skills" :key="skill">{{ skill }}</li>
      </ul>
      <div id="contact" class="contact">
        <span><b>Email:</b> {{ profile.contact.email }}</span>
        <span><b>Телефон:</b> {{ profile.contact.phone }}</span>
      </div>
    </div>
  </section>
</template>

<script setup>
import profile from '../data/profile.json'
</script>