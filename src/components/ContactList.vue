<template>
  <div class="contact-list">
    <div class="contact-item" v-for="contact in contacts" :key="contact.type">
      <i :class="contact.icon"></i>
      <a :href="contact.link" target="_blank">{{ contact.value }}</a>
    </div>
  </div>
</template>

<script setup>
defineProps(['contacts'])
</script>