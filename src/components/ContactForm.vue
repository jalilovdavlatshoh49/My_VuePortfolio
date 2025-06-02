<template>
  <form @submit.prevent="submit" novalidate>
    <div style="margin-bottom:12px">
      <label>Ном:</label>
      <input v-model.trim="form.name" type="text" required />
    </div>
    <div style="margin-bottom:12px">
      <label>Email:</label>
      <input v-model.trim="form.email" type="email" required />
    </div>
    <div style="margin-bottom:12px">
      <label>Паём:</label>
      <textarea v-model.trim="form.message" required></textarea>
    </div>
    <button type="submit">Фиристодан</button>
    <p v-if="sent" style="color:var(--accent)">Паём фиристода шуд!</p>
  </form>
</template>

<script setup>
import { ref } from 'vue'
const form = ref({ name: '', email: '', message: '' })
const sent = ref(false)

function submit() {
  if (!form.value.name || !form.value.email || !form.value.message) return
  sent.value = true
  setTimeout(() => (sent.value = false), 3000)
  form.value = { name: '', email: '', message: '' }
}
</script>

<style scoped>
form {
  max-width: 370px;
  margin-top: 30px;
  display: flex;
  flex-direction: column;
}
input, textarea {
  width: 100%;
  padding: 7px 9px;
  border-radius: 6px;
  border: 1px solid #ccc;
  margin-top: 3px;
  font-size: 1rem;
}
button {
  margin-top: 10px;
  background: var(--accent);
  color: #fff;
  border: none;
  padding: 9px 0;
  border-radius: 6px;
  cursor: pointer;
  font-weight: 600;
}
</style>