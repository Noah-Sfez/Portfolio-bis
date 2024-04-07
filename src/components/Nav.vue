<script setup>
import { RouterLink, RouterView } from 'vue-router';
export default {
  name: 'Nav',
  }

</script>

<template>


</template>

<style scoped>
.linknav {
 color: white;
 font-size: 1.2rem;
}

nav{
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding: 1rem;
  background-color: rgba(22, 22, 23, 0.8);
  width: 100%;
  gap: 1%;
  color: white !important;
}

a {
  margin-right: 10%;
}

</style>