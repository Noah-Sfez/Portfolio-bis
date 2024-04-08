<template>
  <Carousel
    :items-to-show="3"
    :items-to-scroll="1"
    :wrap-around="true"
    :autoplay="3000"
    :pauseAutoplayOnHover="true"
    :perPageCustom="[[768, 1]]" :scrollPerPage="true"
  >
    <Slide v-for="(slide, index) in slides" :key="index">
      <div class="carousel__item">
        <img :src="slide.image" :alt="slide.altText" :class="slide.class" />
        <p>{{ slide.text }}</p>
        <a href="#" class="carousel-link" @click.prevent="openPopup(slide)">En savoir plus ></a>
      </div>
    </Slide>
    <template #addons>
      <Navigation />
    </template>
  </Carousel>
  <div v-if="isPopupVisible" class="overlay" @click="closePopup">
  <div class="popup" @click.stop>
    <h3>{{ selectedSlide.text }}</h3>
    <h4>{{ selectedSlide.undertitle }}</h4>
    <img :src="selectedSlide.image" :alt="selectedSlide.altText" class="pop-img" />
    <p>{{ selectedSlide.pop }}</p>
    <div class="technologies">
      <img v-for="tech in selectedSlide.technologies" :src="tech.icon" :alt="tech.name" :title="tech.name" :class=tech.class />
    </div>
    <div v-if="selectedSlide.apis && selectedSlide.apis.length > 0">
      <h4>APIs utilisées :</h4>
      <ul>
        <li v-for="api in selectedSlide.apis">{{ api.name }} : {{ api.apiText }}</li>
      </ul>
    </div>
    <div v-if="selectedSlide.librairie && selectedSlide.librairie.length > 0">
      <h4>Librairies utilisées :</h4>
      <ul>
        <li v-for="librairie in selectedSlide.librairie">{{ librairie.name }} : {{ librairie.text }}</li>
      </ul>
    </div>
    <div v-if="selectedSlide.link">
      <a :href="selectedSlide.link" target="_blank"><button class="button">
  <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
  <path d="M12 0.296997C5.37 0.296997 0 5.67 0 12.297C0 17.6 3.438 22.097 8.205 23.682C8.805 23.795 9.025 23.424 9.025 23.105C9.025 22.82 9.015 22.065 9.01 21.065C5.672 21.789 4.968 19.455 4.968 19.455C4.422 18.07 3.633 17.7 3.633 17.7C2.546 16.956 3.717 16.971 3.717 16.971C4.922 17.055 5.555 18.207 5.555 18.207C6.625 20.042 8.364 19.512 9.05 19.205C9.158 18.429 9.467 17.9 9.81 17.6C7.145 17.3 4.344 16.268 4.344 11.67C4.344 10.36 4.809 9.29 5.579 8.45C5.444 8.147 5.039 6.927 5.684 5.274C5.684 5.274 6.689 4.952 8.984 6.504C9.944 6.237 10.964 6.105 11.984 6.099C13.004 6.105 14.024 6.237 14.984 6.504C17.264 4.952 18.269 5.274 18.269 5.274C18.914 6.927 18.509 8.147 18.389 8.45C19.154 9.29 19.619 10.36 19.619 11.67C19.619 16.28 16.814 17.295 14.144 17.59C14.564 17.95 14.954 18.686 14.954 19.81C14.954 21.416 14.939 22.706 14.939 23.096C14.939 23.411 15.149 23.786 15.764 23.666C20.565 22.092 24 17.592 24 12.297C24 5.67 18.627 0.296997 12 0.296997Z" fill="white"></path>
  </svg>
  <p class="text">Click me</p>
</button></a>
    </div>
    <div v-if="selectedSlide.site">
      <a :href="selectedSlide.site" target="_blank"><button class="learn-more">
        <span class="circle" aria-hidden="true">
        <span class="icon arrow"></span>
        </span>
        <span class="button-text">Voir le site</span>
      </button></a>
    </div>
    <button @click="closePopup">Fermer</button>
  </div>
</div>
</template>
<script>
import { defineComponent, ref, onMounted, onUnmounted, computed } from 'vue';
import { Carousel, Navigation, Slide } from 'vue3-carousel';
import 'vue3-carousel/dist/carousel.css';
export default defineComponent({
  name: 'WrapAround',
  components: {
    Carousel,
    Slide,
    Navigation,
  },
  setup() {
    const windowWidth = ref(window.innerWidth);
    const itemsToShow = computed(() => {
      return windowWidth.value < 768 ? 1 : 2.5; // Affiche 1 élément pour les écrans < 768px, sinon 2.5
    });
    const handleResize = () => {
      windowWidth.value = window.innerWidth;
    };
    onMounted(() => {
      window.addEventListener('resize', handleResize);
    });
    onUnmounted(() => {
      window.removeEventListener('resize', handleResize);
    });
    return {
      windowWidth,
      itemsToShow,
    };
  },
  data() {
    return {
      slides: [
        
        {
          image: new URL('@/assets/images/sentimental-screen.png', import.meta.url), altText: 'Description of image 2', class: '', text: 'Sentimental AI', undertitle: 'Positif ou négatif.', pop: "Sentimental AI est un site qui permet d'analyser si des commentaires ou du texte en général a un ton plutôt positif ou négatif. Ce site a été réalisé dans le 4 cadre d'un cours sur l'intelligence artificielle à l'IIM Digital School. Nous avons utilisé la librairie Sentimental afin de réaliser ce site. Nous avions une matinée pour réaliser ce projet et il est aujourd'hui opérationnel.",
          link: 'https://github.com/Noah-Sfez/Sentimental-AI',
          technologies: [
            { name: 'HTML', icon: new URL('@/assets/images/html.png', import.meta.url), class: 'html' },
            { name: 'CSS', icon: new URL('@/assets/images/css.png', import.meta.url), class: 'css' },
            { name: 'Javascript', icon: new URL('@/assets/images/javascript.png', import.meta.url), class: 'javascript' },
          ],
          apis: [
          ],
          librairie: [
            { name: 'Sentimental', text: "Utilisation de la librairie afin de reconnaître le sentiment des commentaires rentrés dans l'application web." },
          ],
        },
        {
          image: new URL('@/assets/images/kermony-screen.png', import.meta.url), altText: 'Description of image 2', class: '', text: 'Kermony Office', undertitle: 'Un back office rentable.', pop: "J'ai réalisé ce back-office pour l'entreprise Kermony Office. Ils avaient besoin d'un endroit ou stocker toutes les données concernant la santé financière de leur client, ainsi que d'un outil pour générer des pdf personnalisés. Egalement, ils souhaitaient une API pour pouvoir utiliser ces données avec leur application web en cours de développement. Je leur ai donc réalisé ce back-office avec que des speed meters personnalisés pour les pdf suite à la réalisation d'une équipe de design. J'ai réalisé ce projet en 4 semaines. ",
          technologies: [
            { name: 'HTML', icon: new URL('@/assets/images/html.png', import.meta.url), class: 'html' },
            { name: 'CSS', icon: new URL('@/assets/images/css.png', import.meta.url), class: 'css' },
            { name: 'Javascript', icon: new URL('@/assets/images/javascript.png', import.meta.url), class: 'javascript' },
            { name: 'php', icon: new URL('@/assets/images/php.png', import.meta.url), class: 'php' },
            { name: 'MySQL', icon: new URL('@/assets/images/mysql.png', import.meta.url), class: 'mysql' }
          ],
          librairie: [
            { name: 'JSPDF', text: "Génération de pdf dynamique et personnalisé." },
            { name: 'HTML2CANVAS', text: "Capture d'écran de la page web pour pousser la personnalisation du pdf."}
          ],
          apis: [
            { name: 'API Kermony', apiText: "Création d'une API leur permettant d'utiliser les données de ce back office avec leur application web en cours de développement." },
          ],
        },
        {
          image: new URL('@/assets/images/mascotte-screen.png', import.meta.url), altText: 'Description of image 2', class: 'mascotte-img', text: 'Musée du Jouet', undertitle: "Se moderniser en s'amusant.", pop: "Ce site a pour objectif de moderniser le Musée du Jouet de Poissy en permettant aux visiteurs du musée de créer leur mascotte. J'ai eu la chance de diriger ce projet avec une équipe de 10 personnes comprenant des designeurs, des développeurs et des marketeurs. Ce projet a été réalisé en 8 semaines dans le cadre de la Bourse au Projet de mon école, l'IIM Digital School.",
          technologies: [
            { name: 'HTML', icon: new URL('@/assets/images/html.png', import.meta.url), class: 'html' },
            { name: 'CSS', icon: new URL('@/assets/images/css.png', import.meta.url), class: 'css' },
            { name: 'Javascript', icon: new URL('@/assets/images/javascript.png', import.meta.url), class: 'javascript' },
            { name: 'php', icon: new URL('@/assets/images/php.png', import.meta.url), class: 'php' },
            { name: 'MySQL', icon: new URL('@/assets/images/mysql.png', import.meta.url), class: 'mysql' }
          ],
          librairie: [
            { name: 'HTML2CANVAS', text: "Capture d'écran des mascottes afin de les stocker et de les publier dans une galerie." },
          ],
          apis: [
          ],
        },
        {
          image: new URL('@/assets/images/nosa-screen.png', import.meta.url), altText: 'Description of image 2', class: '', text: 'Nosa Coach', undertitle: 'Un site avec du style.', pop: 'Nosa Coach est un site vitrine réalisé pour une conseillère en image. La cliente souhaitait un site qui mettait en avant ses offres et ses services. J\'ai utilisé la méthode agile pour la confection de ce site web, afin qu\'il convienne au mieux à la cliente. Pour les maquettes Figma ainsi que le développement du site, cela m\'a pris environ 2 semaines.',
          site:'https://nosacoach.com/',
          technologies: [
            { name: 'HTML', icon: new URL('@/assets/images/html.png', import.meta.url), class: 'html' },
            { name: 'CSS', icon: new URL('@/assets/images/css.png', import.meta.url), class: 'css' },
            { name: 'Javascript', icon: new URL('@/assets/images/javascript.png', import.meta.url), class: 'javascript' },
          ],
          apis: [
          ],
        },
        {
          image: new URL('@/assets/images/pokemon-screen.png', import.meta.url), altText: 'Description of image 2', class: '', text: 'Pokemon Shop', undertitle: 'Achetez-les tous.', pop: 'Pokemon Shop est un faux site e-commerce de pokemon. Réalisé dans le cadre de mes études à l\'IIM Digital School, ce site a pour but de mettre en pratique les connaissances acquises en Javascript. J\'ai utilisé l\'API Pokemon pour récupérer toutes les données des Pokemons et les afficher sur le site. J\'ai également développé un panier d\'achat et un système de filtre pour les Pokemons. Ce projet a été réalisé en 1 semaine.',
          site:'https://noah-sfez.github.io/pokemon-shop-API/',
          technologies: [
            { name: 'HTML', icon: new URL('@/assets/images/html.png', import.meta.url), class: 'html' },
            { name: 'CSS', icon: new URL('@/assets/images/css.png', import.meta.url), class: 'css' },
            { name: 'Javascript', icon: new URL('@/assets/images/javascript.png', import.meta.url), class: 'javascript' },
          ],
          apis: [
            { name: 'Pokemon API', apiText:"Utilisation de l'api Pokemon afin de récupérer toutes les données des Pokemons pour pouvoir les afficher et développer les différentes fonctionnalités du site" },
          ],
        },
      ],
      selectedSlide: null,
      isPopupVisible: false,
    };
  },
  methods: {
    openPopup(slide) {
      this.selectedSlide = slide;
      this.isPopupVisible = true;
      document.body.classList.add('no-scroll');
      // mettre un overflow hidden sur le body pour éviter le scroll
      document.body.style.overflow = 'hidden';
      this.$nextTick(() => {
        const overlay = document.querySelector('.overlay');
        if (overlay) {
          overlay.classList.add('open');
          overlay.classList.remove('close'); // Enlève la classe 'close' au cas où elle est présente
        }
      });
    },
    closePopup() {
      const overlay = document.querySelector('.overlay');
      if (overlay) {
        overlay.classList.add('close');
        overlay.classList.remove('open'); // Enlève la classe 'open'
      }
      setTimeout(() => {
        this.isPopupVisible = false;
        document.body.classList.remove('no-scroll');
      }, 500); // Doit correspondre à la durée de l'animation CSS
      document.body.style.overflow = 'auto'; // Remettre le scroll sur le body
    },
  },
  beforeUnmount() {
    document.body.classList.remove('no-scroll');
  }
});
</script>
<style scoped>
/* Button Github */
.button {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px 15px;
  gap: 15px;
  background-color: #181717;
  outline: 3px #181717 solid;
  outline-offset: -3px;
  border-radius: 5px;
  border: none;
  cursor: pointer;
  transition: 400ms;
}
.button .text {
  color: white;
  font-weight: 700;
  font-size: 1em;
  transition: 400ms;
}
.button svg path {
  transition: 400ms;
}
.button:hover {
  background-color: transparent;
}
.button:hover .text {
  color: #181717;
}
.button:hover svg path {
  fill: #181717;
}
/* END BTN GITHUB */
/* Button Learn More */
button {
 position: relative;
 display: inline-block;
 cursor: pointer;
 outline: none;
 border: 0;
 vertical-align: middle;
 text-decoration: none;
 background: transparent;
 padding: 0;
 font-size: inherit;
 font-family: inherit;
}
button.learn-more {
 width: 12rem;
 height: auto;
}
button.learn-more .circle {
 transition: all 0.45s cubic-bezier(0.65, 0, 0.076, 1);
 position: relative;
 display: block;
 margin: 0;
 width: 3rem;
 height: 3rem;
 background: #282936;
 border-radius: 1.625rem;
}
button.learn-more .circle .icon {
 transition: all 0.45s cubic-bezier(0.65, 0, 0.076, 1);
 position: absolute;
 top: 0;
 bottom: 0;
 margin: auto;
 background: #fff;
}
button.learn-more .circle .icon.arrow {
 transition: all 0.45s cubic-bezier(0.65, 0, 0.076, 1);
 left: 0.625rem;
 width: 1.125rem;
 height: 0.125rem;
 background: none;
}
button.learn-more .circle .icon.arrow::before {
 position: absolute;
 content: "";
 top: -0.29rem;
 right: 0.0625rem;
 width: 0.625rem;
 height: 0.625rem;
 border-top: 0.125rem solid #fff;
 border-right: 0.125rem solid #fff;
 transform: rotate(45deg);
}
button.learn-more .button-text {
 transition: all 0.45s cubic-bezier(0.65, 0, 0.076, 1);
 position: absolute;
 top: 0;
 left: 0;
 right: 0;
 bottom: 0;
 padding: 0.75rem 0;
 margin: 0 0 0 1.85rem;
 color: #282936;
 font-weight: 700;
 line-height: 1.6;
 text-align: center;
 font-size: 1rem;
 text-transform: uppercase;
}
button:hover .circle {
 width: 100%;
}
button:hover .circle .icon.arrow {
 background: #fff;
 transform: translate(1rem, 0);
}
button:hover .button-text {
 color: #fff;
}
/* END BTN LEARN MORE */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: scale(0.95);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}
@keyframes fadeOut {
  from {
    opacity: 1;
    transform: scale(1);
  }
  to {
    opacity: 0;
    transform: scale(0.95);
  }
}
.technologies {
  display: flex;
  justify-content: center;
  margin-top: 20px; 
}
.tech-icon {
  width: 30px;
  height: 30px; 
  margin: 0 5px; 
}
.html {
  padding: 10px;
  width: 60px; 
  height: 60px; 
  margin: 0 10px; 
}
.css {
  padding: 10px;
  width: 60px; 
  height: 60px; 
  margin: 0 10px; 
}
.javascript {
  padding: 10px;
  width: 60px; 
  height: 60px; 
  margin: 0 10px; 
}
.php {
  padding: 10px;
  width: 60px; 
  height: 60px; 
  margin: 0 10px; 
}
.mysql {
  padding: 10px;
  width: 60px; 
  height: 60px;
  margin: 0 10px; 
}
.pop-img {
  width: 50%;
  height: auto;
  display: block;
  object-fit: cover;
  max-width: none;
}
.no-scroll {
  overflow: hidden !important;
  height: 100%;
}
.overlay {
  position: fixed; 
  display: none; 
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.5); 
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 50; 
}
/* Classe pour gérer l'état 'ouvert' de la pop-up */
.overlay.open {
  display: flex;
  animation: fadeIn 0.5s forwards; 
}
.overlay.close {
  animation: fadeOut 0.5s forwards; 
}
.popup {
  position: fixed;
  left: 50%;
  top: 50%;
  height: 90%;
  width: auto;
  transform: translate(-50%, -50%);
  z-index: 100;
  background: rgb(255, 255, 255);
  padding: 3% 2% 2% 2%; /* haut, droite, bas, gauche */
  border-radius: 5px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
  justify-content: center;
  overflow-y: scroll;
}
.popup h3 {
  margin-top: 10%;
  color: var(--vt-c-black-text);
  font-size: 2rem;
}
.popup h4 {
  color: var(--vt-c-black-text);
}
.popup p {
  color: var(--vt-c-black-text);
}
.mascotte-img {
  aspect-ratio: 16/9; 
  display: block; 
  object-fit: cover;
  max-width: none;
}
.carousel__item img {
  aspect-ratio: 16/9; 
  width: 100%;
  height: auto;
  display: block; 
  object-fit: cover;
  max-width: none;
}
.carousel__item p {
  transition: transform 0.3s ease;
  transform: translateY(0px); 
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  margin: 0;
  padding: 10px 20px; 
  color: white; 
  font-size: 1.2em; 
  z-index: 10; 
  text-align: center; 
}
.carousel__item::after {
  content: '';
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: 50%; 
  background: linear-gradient(to top, rgba(0, 0, 0, 0.7), transparent); 
}
.carousel {
  width: 100%;
  height: auto;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgb(255, 255, 255);
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
  margin: 0 2%; 
  background-color: var(--vc-clr-black);
  color: var(--vc-clr-white);
  font-size: 20px;
  border-radius: 8px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  overflow: hidden; 
}
.carousel__slide {
  padding: 0;
  width: 50% !important;
  height: auto !important;
}

.carousel__item a {
  opacity: 0; 
  transition: opacity 0.3s ease;
  color: var(--vt-c-blue-dark);
  z-index: 999;
}
.carousel__item:hover p {
  transform: translateY(-30px);
  opacity: 1; 
}
.carousel__item:hover a {
  opacity: 1; 
}
.carousel-link {
  position: absolute;
  bottom: 10px; /* Ou à la distance souhaitée du bas de l'image */
  left: 50%;
  transform: translateX(-50%);
  color: white;
  text-decoration: none;
}
@media screen and (max-width: 768px) {
  .carousel__slide {
    width: 100% !important; /* Assure que chaque slide prend toute la largeur */
  }
  .carousel__viewport {
  display: flex;
  justify-content: center; 
  align-items: center; 
}


  .carousel__item {
    margin: 0 5px; 
    box-sizing: border-box; 
    width: 100%;
  }

  /* Assure-toi que les images dans les slides sont aussi ajustées en conséquence */
  .carousel__item img {
    width: 100%;
    height: auto;
  }
  .carousel__prev,
  .carousel__next {
    width: 40px;
    height: 40px;
    font-size: 35px;
  }
  .carousel-link {
    font-size: 0.8em;
  }
  .carousel__item p {
    font-size: 1em;
  }
  .overlay.open {
  display: flex; /* ou 'block', selon ce qui convient à ton layout */
  animation: fadeIn 0.5s forwards; /* Utilise l'animation fadeIn quand la pop-up s'ouvre */
}
.overlay.close {
  animation: fadeOut 0.5s forwards; /* Utilise l'animation fadeOut quand la pop-up se ferme */
}
}

</style>