<template>
  <section class="card stack-section">
    <div class="category">
      <h2 class="section-title">Языки программирования</h2>
      <ul class="tag-list">
        <li v-for="lang in profile.languages" :key="lang" class="tag">
          {{ lang }}
        </li>
      </ul>
    </div>

    <div class="category">
      <h2 class="section-title">Фреймворки и технологии</h2>
      <ul class="tag-list">
        <li v-for="fw in profile.frameworks" :key="fw" class="tag">
          {{ fw }}
        </li>
      </ul>
    </div>
  </section>
</template>

<script setup>
import profile from '../data/profile.json'
</script>

<style scoped>
.stack-section {
  width: 100%;
  max-width: 720px;
  margin: auto;
  padding: 20px 16px;
  box-sizing: border-box;
  font-family: 'Inter', sans-serif;
  color: var(--text-color);
}

/* Заголовки */
.section-title {
  font-size: 1.3rem;
  font-weight: 600;
  margin: 24px 0 12px;
  color: var(--text-color);
}

/* Списки */
.tag-list {
  list-style: none;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-bottom: 16px;
}

/* Теги */
.tag {
  background-color: var(--chip-bg);
  color: var(--chip-text);
  padding: 7px 14px;
  border-radius: 18px;
  font-size: 0.95rem;
  box-shadow: 0 3px 10px rgba(80, 120, 200, 0.25); /* ❗️Бештар соягирӣ */
  transition: all 0.3s ease;
}

.tag:hover {
  background-color: var(--accent-color);
  color: #fff;
}

/* Адаптив */
@media (max-width: 600px) {
  .section-title {
    font-size: 1.15rem;
  }

  .tag {
    font-size: 0.85rem;
    padding: 6px 12px;
  }
}
</style>
