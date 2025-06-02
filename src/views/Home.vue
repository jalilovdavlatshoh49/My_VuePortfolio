<template>
  <section style="text-align:center; margin-top:20px;">
    <img class="avatar" :src="data.avatar" alt="Avatar" />
    <h1>Салом, ман {{ data.name }}</h1>
    <h2 style="color:var(--accent)">{{ data.title }}</h2>
    <p style="max-width:500px; margin:0 auto">{{ data.about }}</p>
    <a href="/Davlatshoh_CV.pdf" download class="download-btn" style="display:inline-block;margin:24px 0 0 0;padding:9px 18px;background:var(--accent);color:#fff;border-radius:8px;text-decoration:none;font-weight:600">⬇️ Download CV</a>
  </section>
</template>

<script setup>
import data from '../assets/data.json'
</script>