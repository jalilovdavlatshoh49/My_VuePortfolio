<template>
  <hr class="divider" />
</template>

<style scoped>
.divider {
  height: 2px;
  background: linear-gradient(
    to right,
    transparent,
    var(--divider-color),
    transparent
  );
  border: none;
  margin: 2rem 0;
  opacity: 0.8;
  transition: background-color 0.3s ease, opacity 0.3s ease;
}
</style>
