<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
      <nav>
        <RouterLink to="/experience">Expériences</RouterLink>
        <RouterLink to="/projets">Projets</RouterLink>
        <RouterLink to="/contact">Contact</RouterLink>
      </nav>
  </header>

  <RouterView />
</template>

<style scoped>
nav{
  display: flex;
  justify-content: flex-end;
  padding: 1rem;
  background-color: rgba(22, 22, 23, 0.8);
  width: 100%;
  gap: 1%;
}
a {
  margin-right: 10%;
}
</style>
