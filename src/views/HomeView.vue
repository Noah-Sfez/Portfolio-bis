<script>
import Caroussel from '../components/Caroussel.vue';
import Timeline from '../components/Timeline.vue';
import Form from '../components/Form.vue';

export default {
  components: {
    Caroussel,
    Timeline,
    Form
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
                data-aos-easing="ease-in-sine">Noah SFEZ</h1>
      <div class="underTitle">
        <p>Développeur fullstack.</p>
        <RouterLink to="/contact">Contacter ></RouterLink>
      </div>
      <img src="../assets/images/photo-presentation 2.png" alt="Photo-de-profil" data-aos="fade-up"
     data-aos-duration="3000">
    </div>
    <!-------------------------------- Expériences ---------------------------->
    <Timeline id="timeline" />
    <!-------------------------------- Caroussel ---------------------------->
    <!--<h2 class="title-project">Mes projets.</h2>-->
    <Caroussel ref="projetsRef" />

    <!-------------------------------- Form ---------------------------->
    <Form data-aos="fade-up"
     data-aos-easing="ease-in-sine"
     data-aos-offset="400"
     data-aos-duration="1200"
     />
    
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
  .title-project {
    text-align: center;
    font-size: 2rem;
    color: var(--vt-c-black-text);
    margin-top: 5%;
  }

@media screen and (max-width: 768px) {
  h1 {
    font-size: 2rem;
  }
  p {
    font-size: 1rem;
  }
  a {
    font-size: 1rem;
  }
  img {
    width: 40%;
  }
}

</style>
