<template>
  <section class="profile-card">
    <img src="./assets/profile.jpg" alt="Аватар" class="profile-img" />
    <div class="profile-info">
      <!-- Имя профиля по центру -->
      <h1 class="profile-name">{{ profile.name }}</h1>
      <p class="about">{{ profile.about }}</p>
    </div>
  </section>
</template>

<script setup>
// Импортируем данные профиля
import profile from '../data/profile.json'
</script>

<style scoped>
.profile-card {
  background: #fff;
  border-radius: 20px;
  box-shadow: 0 6px 30px rgba(36, 86, 166, 0.10);
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 36px 16px 24px 16px;
  margin-bottom: 18px;
}
.profile-img {
  width: 110px;
  height: 110px;
  object-fit: cover;
  border-radius: 50%;
  border: 3px solid #5686e0;
  margin-bottom: 18px;
  box-shadow: 0 2px 18px rgba(86,134,224,0.16);
}
.profile-info {
  text-align: center;
}
.profile-name {
  font-size: 1.5em;
  color: #234;
  margin: 0 0 7px 0;
  font-weight: 700;
  letter-spacing: 0.01em;
}
.about {
  font-size: 1.05em;
  color: #4d6075;
  text-align: center;
  margin: 0;
}
</style>
