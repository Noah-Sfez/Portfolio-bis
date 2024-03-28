<script setup>
import { RouterLink, RouterView } from 'vue-router';


</script>
<template>
  <header>
    <nav>
      <RouterLink to="/" class="linknav">Home</RouterLink>
      <RouterLink to="/experience" class="linknav">Expériences</RouterLink>
      <RouterLink to="/contact" class="linknav">Contact</RouterLink>
    </nav>
  </header>
  <RouterView/>
  <footer>
    <div>
      <h4>Contact</h4>
      <a href="mailto:sfz.noah@gmail.com" class="mail" target="_blank">sfz.noah@gmail.com</a>
      <p>06 99 51 05 91</p>
    </div>
    <h3>N'hésitez pas à me contacter</h3>
    <div class="icones">
      <a href="https://github.com/Noah-Sfez" target="_blank"><img src="./assets/images/github.png" alt="github"></a>
      <a href="https://www.linkedin.com/in/noahsfez/" target="_blank"><img src="./assets/images/linkedin.png" alt="linkedin"></a>
    </div>
  </footer>
</template>
<style scoped> 
.linknav {
 color: white;
 font-size: 1.2rem;
}
nav{
  display: flex;
  justify-content: flex-end;
  padding: 1rem;
  background-color: rgba(22, 22, 23, 0.8);
  width: 100%;
  gap: 1%;
  position: sticky;
  position: -webkit-sticky; /* Pour le support Safari */
  top: 0;
  z-index: 1000;
  color: white !important;
}
a {
  margin-right: 10%;
}
footer {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  justify-content: center;
  justify-items: center;
  align-items: center;
  background-color: rgb(245, 245, 247);
  padding: 1rem;
  gap: 1%;
}

.mail {
  color: black;
  text-decoration: none;
}

.icones {
  display: flex;
  justify-content: center;
  gap: 1rem;
}
.icones img {
  width: 3rem;
  height: auto;
}

@media screen and (max-width: 768px) {
  nav {
    justify-content: center;
    gap: 40px;
  }
  a {
    margin-right: 0;
  }
  footer {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  .icones {
    justify-content: center;
  }
}
  


</style>

