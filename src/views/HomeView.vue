<script>
import Caroussel from '../components/Caroussel.vue';

export default {
  components: {
    Caroussel,
  },
};

</script>

<template>
  <main>
    <!-------------------------------- Presentation ---------------------------->
    <div class="firstDiv">
      <h1>Noah SFEZ</h1>
      <div class="underTitle">
        <p>Développeur fullstack.</p>
        <RouterLink to="/contact">Contacter ></RouterLink>
      </div>
      <img src="../assets/images/photo-presentation 2.png" alt="Photo-de-profil">
    </div>
    <!-------------------------------- Expériences ---------------------------->
    <div class="experiences">
      <h2>Expériences</h2>
      <p class="xp-text">Pousser les limites de la technologie.</p>
      <RouterLink to="/experience">Voir le détail des expériences ></RouterLink>
      <div class="timeline">
        <div class="timeline-item">
          <div class="timeline-content">
            <h3 class="underline">Décembre 2023 - Aujourd'hui</h3>
            <p class="white-text">Kermony Office  Back-end</p>
          </div>
        </div>
        <div class="timeline-item">
          <div class="timeline-content">
            <h3 class="underline">Octobre - Décembre 2023</h3>
            <p class="white-text">Musée du Jouet  Chef de Projet</p>
          </div>
        </div>
        <div class="timeline-item">
          <div class="timeline-content">
            <h3 class="underline">Juillet 2023</h3>
            <p class="white-text">Nosa Coach  Fullstack</p>
          </div>
        </div>
        <div class="timeline-item">
          <div class="timeline-content">
            <h3 class="underline">Décembre 2018</h3>
            <p class="white-text">Stage chez Flowerbox</p>
          </div>
        </div>
      </div>
    </div>
    <!-------------------------------- Projets ---------------------------->
    <div class="projets">
      <div class="pokemon projet background-black">
        <h2>Pokemon Shop</h2>
        <p class="white-text">Achetez-les tous.</p>
        <RouterLink to="/projets">En savoir plus >></RouterLink>
        <img class="screen-grid" src="../assets/images/pokemon-screen.png" alt="">
      </div>
      <div class="mongoo projet">
        <h2 class="black-text">Mongoo</h2>
        <p>Le visuel qui donne faim.</p>
        <RouterLink to="/projets">En savoir plus >></RouterLink>
        <img class="screen-grid" src="../assets/images/mongoo-screen.png" alt="">
      </div>
      <div class="projet">
        <h2 class="black-text">Création de mascottes</h2>
        <p>Se moderniser en s'amusant.</p>
        <RouterLink to="/projets">En savoir plus >></RouterLink>
        <img class="screen-grid mascotte" src="../assets/images/mascotte-screen.png" alt="">
      </div>
      <div class="nosa projet background-black">
        <h2>Nosa Coach</h2>
        <p class="white-text">Un site avec du style.</p>
        <RouterLink to="/projets">En savoir plus >></RouterLink>
        <img class="screen-grid" src="../assets/images/nosa-screen.png" alt="">
      </div>
    </div>
    <!-------------------------------- Caroussel ---------------------------->
    <Caroussel />
    
  </main>
</template>

<style scoped>

/* -------------- Welcome ---------------- */
  .firstDiv {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: auto;
    margin-top: 8%;
    gap: 0;
  }
  .underTitle {
    margin-top: 5%;
  }
  h1 {
    font-size: 3rem;
    color: var(--vt-c-black-text);
  }
  p {
    text-align: center;
    font-size: 1.5rem;
    color: var(--vt-c-black-text);
  }
  a {
    display: block;
    margin-top: 2rem;
    text-align: center;
    font-size: 1.5rem;
    color: var(--vt-c-blue-light);
  }
  img {
    width: 15.5%;
    height: auto;
  }

/* ---------------- Experiences ----------------- */

.experiences {
  background-color: black;
  height: auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
}

h2 {
  font-size: 3rem;
  color: var(--vt-c-white-light);
  margin-top: 5%;
}

.xp-text {
  font-size: 1.5rem;
  color: var(--vt-c-white-light);
  margin-top: 1%;
}

/* -------------- Timeline ----------------- */

.timeline {
  position: relative;
  max-width: 1200px;
  margin: 5% 0;
  padding: 50px 0;
}

.timeline:before {
  content: '';
  position: absolute;
  top: 0;
  bottom: 0;
  width: 10px;
  background: #f7f7f7;
  left: 50%;
  margin-left: -1.5px;
}

.timeline-item {
  padding: 20px 0;
  position: relative;
  width: 50%;
  margin-bottom: 20px;
  color: var(--vt-c-white-light);
}

.timeline-item:nth-child(odd) {
  float: right;
  text-align: left;
  margin-right: -45px;
}

.timeline-item:nth-child(even) {
  float: left;
  text-align: right;
  margin-left: 240px;
}

.timeline-content {
  position: relative;
  width: 45%;
  color: var(--vt-c-white-light);
  padding: 20px;
}

.white-text {
  color: var(--vt-c-white-light);
}

.underline {
  text-decoration: underline;
  color: var(--vt-c-white-light);
}

/* ---------------- Projets ----------------- */

.projets {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 5%;
  margin: 5%;
}

.black-text {
  color: var(--vt-c-black-text);
}

.projet {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1%;
  padding: 2%;
  border-radius: 10px;
  color: var(--vt-c-white-light);
}

.background-black {
  background-color: black;
}

.mascotte{
  width: 70% !important;
  height: auto;
} 

.screen-grid {
  margin-top: 5%;
  width: 80%;
  height: auto;
  border-radius: 10px;
}

/* ---------------- Caroussel ----------------- */

.caroussel {
  display: flex;
  justify-content: space-around;
  margin: 5% 0;
  height: 70vh;
  background-color: black;
  position: relative;
}

.caroussel-projects {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1%;
  padding: 2%;
  border-radius: 10px;
  color: var(--vt-c-white-light);
}

.img-caroussel {
  width: 60%;
  height: auto;
  border-radius: 10px;
  position: absolute;
}


</style>
