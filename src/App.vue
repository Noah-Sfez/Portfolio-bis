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
  <footer>
    <div>
      <h4>Contact</h4>
      <a href="mailto:sfz.noah@gmail.com" class="mail" target="_blank">sfz.noah@gmail.com</a>
      <p>06 99 51 05 91</p>
    </div>
    <h3>N'hésitez pas à me contacter</h3>
    <div>
      <a href="" target="_blank"><img src="" alt="github"></a>
      <a href="https://www.linkedin.com/in/noah-sfez-3b3b3b1b3/" target="_blank"><img src="../assets/images/linkedin.png" alt="linkedin"></a>
    </div>
  </footer>
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


footer {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  justify-content: center;
  align-items: center;
  background-color: rgb(245, 245, 247);
  padding: 1rem;
  gap: 1%;
}

.mail {
  color: black;
  text-decoration: none;
}
</style>

