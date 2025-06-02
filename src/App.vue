<template>
  <div class="wrapper">
    <!-- Блок профиля -->
    <section class="profile-card">
      <img src="./assets/profile.jpg" alt="Аватар" class="profile-img" />
      <div class="profile-info">
        <h1>{{ profile.name }}</h1>
        <p class="about">{{ profile.about }}</p>
      </div>
    </section>

    <Divider />

    <!-- Блок знаний -->
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

    <Divider />

    <!-- Блок проектов -->
    <section class="card">
      <h2>Проекты на GitHub</h2>
      <div class="projects">
        <div v-for="project in profile.projects" :key="project.title" class="project">
          <a :href="project.link" target="_blank" class="project-title">{{ project.title }}</a>
          <p class="project-desc">{{ project.description }}</p>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
// Импортируем профиль из отдельного JSON-файла
import profile from './data/profile.json'
// Импортируем компонент-разделитель
import Divider from './components/Divider.vue'
</script>

<style>
/* Основной фон и отступы */
body {
  background: linear-gradient(135deg, #e7f0fd 0%, #fafbfd 100%);
  margin: 0;
  font-family: 'Segoe UI', Arial, sans-serif;
}

/* Основной ограничивающий контейнер */
.wrapper {
  max-width: 420px;
  margin: 0 auto;
  padding: 20px 8px 28px 8px;
}

/* Карточка профиля */
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

.profile-info h1 {
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

/* Карточки */
.card {
  background: #fff;
  border-radius: 18px;
  box-shadow: 0 4px 18px rgba(86,134,224,0.10);
  padding: 22px 14px 14px 14px;
  margin-bottom: 18px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

h2 {
  color: #5686e0;
  font-size: 1.1em;
  margin: 0 0 12px 0;
  letter-spacing: 0.01em;
}

/* Чипсы для технологий */
.chips {
  display: flex;
  flex-wrap: wrap;
  gap: 7px;
  list-style: none;
  padding: 0;
  margin: 0 0 16px 0;
}
.chips li {
  background: #e7f0fd;
  color: #234;
  border-radius: 8px;
  padding: 7px 15px;
  font-size: 1em;
  font-weight: 500;
  box-shadow: 0 2px 8px #5686e01a;
  transition: background 0.18s;
}

.projects {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 18px;
}
.project {
  background: #f6fafd;
  border-radius: 12px;
  box-shadow: 0 1px 8px #5686e011;
  padding: 13px 15px;
  text-align: left;
}
.project-title {
  color: #356ee7;
  font-weight: 600;
  font-size: 1.08em;
  text-decoration: none;
  transition: color 0.16s;
}
.project-title:hover {
  color: #234;
  text-decoration: underline;
}
.project-desc {
  color: #3e4c62;
  font-size: 0.97em;
  margin: 4px 0 0 0;
}

/* Divider — разделитель секций */
.divider {
  width: 92%;
  margin: 18px auto;
  height: 2px;
  background: linear-gradient(90deg, transparent 2%, #5686e0 49%, transparent 98%);
  opacity: 0.16;
  border-radius: 1px;
  box-shadow: 0 2px 8px #5686e022;
}

/* Адаптивность для мобильных */
@media (max-width: 480px) {
  .wrapper {
    max-width: 98vw;
    padding: 9px 2vw 18px 2vw;
  }
  .profile-card,
  .card {
    padding: 18px 5vw 14px 5vw;
  }
}
</style>