<template>
  <section>
    <h2>Тамос</h2>
    <ContactList :contacts="data.contacts" />
    <h3 style="margin-top:36px">Паёми худро нависед</h3>
    <ContactForm />
  </section>
</template>

<script setup>
import data from '../assets/data.json'
import ContactList from '../components/ContactList.vue'
import ContactForm from '../components/ContactForm.vue'
</script>