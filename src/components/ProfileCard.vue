<template>
  <section class="card profile-card">
    <!-- Аватар с возможностью увеличения -->
    <div class="image-wrapper" @click="showFullImage = true">
      <img :src="profileImage" alt="Аватар" class="profile-img" />
    </div>

    <div class="profile-info">
      <h1 class="profile-name">{{ profile.name }}</h1>
      <p class="about">{{ profile.about }}</p>
    </div>

    <!-- Модальное окно при клике на изображение -->
    <div v-if="showFullImage" class="modal" @click="showFullImage = false">
      <img :src="profileImage" alt="Аватар" class="modal-img" />
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import profile from '../data/profile.json'
const profileImage = new URL('@/assets/profile.jpg', import.meta.url).href
const showFullImage = ref(false)
</script>

<style scoped>
/* ✅ Комментарии на русском языке */

/* Основной блок карточки */
.profile-card {
  width: 100%;
  max-width: 500px;
  margin: 0 auto;
  text-align: center;
  padding: 20px 16px;
  box-sizing: border-box;
}

/* Обёртка для изображения */
.image-wrapper {
  cursor: pointer;
}

/* Стиль изображения (аватар) */
.profile-img {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  border: 3px solid var(--accent-color);
  object-fit: cover;
  box-shadow: 0 2px 18px var(--card-shadow);
  transition: transform 0.3s ease;
}

.profile-img:hover {
  transform: scale(1.06);
}

/* Информация профиля */
.profile-info {
  padding-top: 12px;
}

.profile-name {
  font-size: 1.8rem;
  font-weight: 700;
  color: var(--text-color);
  margin-bottom: 6px;
}

.about {
  font-size: 1rem;
  color: var(--secondary-color);
  margin: 0;
}

/* Модальное окно */
.modal {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
}

.modal-img {
  max-width: 92vw;
  max-height: 90vh;
  border-radius: 14px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
}

/* Адаптивность */
@media (max-width: 600px) {
  .profile-img {
    width: 90px;
    height: 90px;
  }

  .profile-name {
    font-size: 1.4rem;
  }

  .about {
    font-size: 0.95rem;
  }
}
</style>
