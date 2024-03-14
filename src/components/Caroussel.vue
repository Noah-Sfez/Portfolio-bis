<template>
  <Carousel 
  :items-to-show="2.5" 
  :items-to-scroll="1"
  :wrap-around="true"
  :autoplay="3000"
  :pauseAutoplayOnHover="true"
  :snapAlign="center"
  >
    <Slide v-for="(slide, index) in slides" :key="index">
      <div class="carousel__item">
        <img :src="slide.image" :alt="slide.altText" />
        <p>{{ slide.text }}</p>
      </div>
    </Slide>

    <template #addons>
      <Navigation />
    </template>
  </Carousel>
</template>
<script>
import { defineComponent } from 'vue';
import { Carousel, Navigation, Slide } from 'vue3-carousel';
import 'vue3-carousel/dist/carousel.css';
export default defineComponent({
  name: 'WrapAround',
  components: {
    Carousel,
    Slide,
    Navigation,
  },
  data() {
    return {
      slides: [
        { image: new URL('@/assets/images/seasons-screen.png', import.meta.url), altText: 'Description of image 1', text: 'Seasons' },
        { image: new URL('@/assets/images/kermony-screen.png', import.meta.url), altText: 'Description of image 2', text: 'Kermony Office' },
        { image: new URL('@/assets/images/sentimental-screen.png', import.meta.url), altText: 'Description of image 2', text: 'Sentimental AI' },
      ],
    };
  },
});
</script>
<style>
/* Add any additional styling here */
.carousel__item img {
  width: 100%;
  height: auto;
  display: block; /* Cela supprime l'espace blanc sous l'image */
  object-fit: cover;
  max-width: none;
}
.carousel__item p {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  margin: 0;
  padding: 10px 20px; /* Espace interne pour le texte */
  /*background: linear-gradient(to top, rgba(0, 0, 0, 0.6), transparent); /* Gradient similaire au filtre pour la lisibilité */
  color: white; /* Couleur du texte */
  font-size: 1em; /* Taille du texte */
  z-index: 10; /* S'assurer que le texte est au-dessus de l'image */
  text-align: center; /* Centrer le texte */
}
.carousel__item::after {
  content: '';
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: 50%; /* Ajuste ceci pour contrôler la hauteur du filtre */
  background: linear-gradient(to top, rgba(0, 0, 0, 0.7), transparent); /* Gradient du noir à transparent */
}
.carousel {
  width: 100%;
  height: auto;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: black;
  padding: 2%;
}
.caroussel_viewport {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}
.carousel__item {
  position: relative;
  min-height: 200px;
  width: 100%;
  height: auto;
  margin: 0 2%; /* Ajouté pour assurer l'espacement entre les slides, ajuster selon les besoins */
  background-color: var(--vc-clr-black);
  color: var(--vc-clr-white);
  font-size: 20px;
  border-radius: 8px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  overflow: hidden; /* Pour les coins arrondis */
}
.carousel__slide {
  padding: 0;
  width: 50% !important;
  height: auto !important;
}
.carousel__prev,
.carousel__next {
  box-sizing: content-box;
  color: black;
  width: 100px;
  height: 100px;
  font-size: 50px;
  font-weight: bold;
}
</style>
