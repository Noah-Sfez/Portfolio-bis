<script>
import Caroussel from '../components/Caroussel.vue';
import Timeline from '../components/Timeline.vue';
import Form from '../components/Form.vue';
import CarousselMobile from '../components/CarousselMobile.vue';
import Technos from '../components/Techno.vue';

export default {
  components: {
    Caroussel,
    Timeline,
    Form, 
    CarousselMobile,
    Technos
  },
  methods: {
    handleScrollTo(sectionId) {
      const section = this.$el.querySelector(`#${sectionId}`);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
};
</script>
<template>
  <main>
    <!-------------------------------- Presentation ---------------------------->
    <div class="firstDiv">
      <h1 data-aos="zoom-out-down" data-aos-duration="1500"
                data-aos-easing="ease-in-sine" class="title-general">Noah SFEZ</h1>
      <div class="underTitle">
        <p class="soustitle-general">Développeur fullstack.</p>
        <RouterLink to="/contact">Contacter ></RouterLink>
      </div>
      <img src="../assets/images/photo-presentation 2.png" alt="Photo-de-profil" class="imgprofil"data-aos="fade-up"
     data-aos-duration="3000">
    </div>
    <!-------------------------------- Technos ---------------------------->
    <Technos />
    <!-------------------------------- Caroussel ---------------------------->
    <!--<h2 class="title-project">Mes projets.</h2>-->
    <h2 class="title-project">Mes projets.</h2>
      <p class="title-project-p">Voici une sélection des quelques projets que j'ai pu réaliser jusqu'à maintenant.</p>
      <p class="title-project-p"> Pour en voir davantage, rendez-vous sur mon <a href="https://github.com/Noah-Sfez" target="_blank" class="github-link" style="text-decoration: underline;">Github</a></p>
    <div id="caroussel">
      <Caroussel ref="projetsRef" />
    </div>

    <!-------------------------------- CarousselMobile ---------------------------->
    <div id="carousselMobile">
      <CarousselMobile />
    </div>
    <!-------------------------------- Caroussel ---------------------------->

    <!-------------------------------- Form --------------------------
    <Form data-aos="fade-up"
     data-aos-easing="ease-in-sine"
     data-aos-offset="400"
     data-aos-duration="1200"
     />-->
    
  </main>
</template>

<style>

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
    text-align: center;
  }
  .title-general {
    font-size: 3rem;
    color: var(--vt-c-black-text);
  }
  .soustitle-general {
    text-align: center;
    font-size: 1.5rem;
    color: var(--vt-c-black-text);
  }
  a {
    text-align: center;
    font-size: 1.5rem;
    color: var(--vt-c-blue-light);
  }
  .imgprofil {
    width: 15.5%;
    height: auto;
  }
  .title-project {
    text-align: center;
    font-size: 2rem;
    color: var(--vt-c-black-text);
    margin-top: 5%;
  }
  .title-project-p {
    text-align: center;
    font-size: 1.2rem;
    color: var(--vt-c-black-text);
    margin-top: 2%;
  }

  #carousselMobile {
    display: none;
  }

  .carousel__prev,
.carousel__next {
  box-sizing: content-box;
  color: black;
  background-color: white;
  border: 1px solid black;
  box-shadow: 5px 5px 5px 0px rgba(0, 0, 0, 0.75);
  border-radius: 50%;
  width: 60px;
  height: 60px;
  font-size: 55px;
  font-weight: bold;
  transition: 0.5s;
}
.carousel__prev:hover,
.carousel__next:hover {
  color: white;
  background-color: rgb(0, 0, 0);
}
  

@media screen and (max-width: 768px) {
  h1 {
    margin-top: 20%;
    font-size: 2rem;
  }
  p {
    font-size: 1rem;
  }
  a {
    font-size: 1rem;
  }
  .firstDiv {
    height: 90vh;
    position: relative;
  }

  .imgprofil {
    position: absolute;
    bottom: 0;
    width: 35vh;
  }
  #carousselMobile {
    display: block !important ;
  }
  #caroussel {
    display: none;
  }
  .carousel__prev,
.carousel__next {
  display: none;
}

 .popup {
    width: 90% !important;
    height: 80% !important;
    padding: 10% 2% 2% 2% !important;
    overflow-y: auto !important; /* 'auto' est généralement préférable à 'scroll' */
    overflow-x: hidden !important;
    /* Le reste de vos styles... */
  }


.popup h3 {
  font-size: 1.5rem;
}

.popup p {
  font-size: 0.8rem;
  text-align: center;
}

.popup li {
  font-size: 0.8rem;
  text-align: center;
}

.pop-img {
  width: 200px;
  height: auto;
}
.overlay.open {
  display: flex; /* ou 'block', selon ce qui convient à ton layout */
  animation: fadeIn 0.5s forwards; /* Utilise l'animation fadeIn quand la pop-up s'ouvre */
}
.overlay.close {
  animation: fadeOut 0.5s forwards; /* Utilise l'animation fadeOut quand la pop-up se ferme */
}
.title-project {
  font-size: 1.5rem;
}
.title-project-p {
  font-size: 1rem;
}
}

</style>
