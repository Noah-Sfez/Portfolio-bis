<script>
import CommitGraph from './CommitGraph.vue';
import BackgroundDots from './BackgroundDots.vue';

export default {
  name: 'Project',
  components: {
    CommitGraph,
    BackgroundDots
  },
  data() {
    return {
      isFlipped1: false,
      isFlipped2: false,
      isFlipped3: false,
      currentImageIndex: 0, 
      totalImages: 0, 
    };
  },
  methods: {
    flipCard(cardNumber) {
      if (cardNumber === 1) this.isFlipped1 = !this.isFlipped1;
      else if (cardNumber === 2) this.isFlipped2 = !this.isFlipped2;
      else if (cardNumber === 3) this.isFlipped3 = !this.isFlipped3;
    },
    animateImages() {
      const images = document.querySelectorAll('.project-card-front img'); 
      this.totalImages = images.length; // Stocke le nombre total d'images
      setInterval(() => {
        images[this.currentImageIndex].classList.add('color-animation');
        this.currentImageIndex = (this.currentImageIndex + 1) % this.totalImages;
      }, 4000); 
    }
  },
  mounted() {
    this.animateImages(); 
  }
};
</script>
<template>
  <div class="body project-container">
    <BackgroundDots />
    <CommitGraph />
    <h2>Projets</h2>
    <p>Voici un aperçu de quelques projets que j'ai pu réaliser.</p>
    <div class="projects-container">
      <!-- Projet 1 -->
      <div class="project-card" :class="{ flipped: isFlipped1 }">
        <div class="project-card-inner">
          <!-- Face avant -->
          <div class="project-card-front" :class="{ 'hide-front': isFlipped1 }">
            <h3 class="project-title">Kermony Office | Développeur Full-stack</h3>
            <img src="@/assets/images/kermony-screen.png" alt="">
            <button @click="flipCard(1)">
              <span>En savoir plus</span>
              <span class="icon">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 448 512"
                  class="svg-icon"
                >
                  <path
                    d="M438.6 278.6c12.5-12.5 12.5-32.8 0-45.3l-160-160c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3L338.8 224 32 224c-17.7 0-32 14.3-32 32s14.3 32 32 32l306.7 0L233.4 393.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0l160-160z"
                  ></path>
                </svg>
              </span>
            </button>
          </div>
          <!-- Face arrière -->
          <div class="container project-card-back">
            <div class="terminal_toolbar">
              <div class="butt">
                <button class="btn btn-color"></button>
                <button class="btn"></button>
                <button class="btn"></button>
              </div>
              <p class="user">Kermony Office | Développeur Fullstack ~</p>
              <div class="add_tab">+</div>
            </div>
            <div class="terminal_body">
              <div class="terminal_prompt">
                <span class="terminal_user">@admin:</span>
                <span class="terminal_location">~</span>
                <span class="terminal_bling">$</span>
                <span class="terminal_cursor"></span>
              </div>
              <div class="terminal_output">
                <pre class="output_text">Un back-office a été développé pour Kermony Office, permettant de stocker les données financières des clients, générer des PDF personnalisés, et fournir une API pour leur application web en cours de développement.</pre>
              </div>
              <div class="terminal_input">
                <input placeholder="Type a command..." class="input_text" type="text" />
                <button @click="flipCard(1)">Voir moins <<</button>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- Répète le même code pour les autres projets -->
      <div class="project-card" :class="{ flipped: isFlipped2 }">
        <div class="project-card-inner">
          <div class="project-card-front" :class="{ 'hide-front': isFlipped2 }">
            <h3 class="project-title">Nosa Coach | Développeur Front-end</h3>
            <img src="@/assets/images/nosa-screen.png" alt="">
            <button @click="flipCard(2)">
              <span>En savoir plus</span>
              <span class="icon">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 448 512"
                  class="svg-icon"
                >
                  <path
                    d="M438.6 278.6c12.5-12.5 12.5-32.8 0-45.3l-160-160c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3L338.8 224 32 224c-17.7 0-32 14.3-32 32s14.3 32 32 32l306.7 0L233.4 393.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0l160-160z"
                  ></path>
                </svg>
              </span>
            </button>
          </div>
          <div class="container project-card-back">
            <div class="terminal_toolbar">
              <div class="butt">
                <button class="btn btn-color"></button>
                <button class="btn"></button>
                <button class="btn"></button>
              </div>
              <p class="user">Nosa Coach | Développeur Front-end ~</p>
              <div class="add_tab">+</div>
            </div>
            <div class="terminal_body">
              <div class="terminal_prompt">
                <span class="terminal_user">@admin:</span>
                <span class="terminal_location">~</span>
                <span class="terminal_bling">$</span>
                <span class="terminal_cursor"></span>
              </div>
              <div class="terminal_output">
                <pre class="output_text">Nosa Coach est un site vitrine réalisé pour une conseillère en image, mettant en avant ses offres et services, conçu en utilisant la méthode agile, avec des maquettes Figma et le développement finalisé en environ 2 semaines.</pre>
              </div>
              <div class="terminal_input">
                <input placeholder="Type a command..." class="input_text" type="text" />
                <button @click="flipCard(2)">Voir moins <<</button>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- Répète le même code pour les autres projets -->
      <div class="project-card" :class="{ flipped: isFlipped3 }">
        <div class="project-card-inner">
          <div class="project-card-front" :class="{ 'hide-front': isFlipped3 }">
            <h3 class="project-title">Musée du Jouet de Poissy | Chef de projet</h3>
            <img src="@/assets/images/mascotte-screen.png" alt="">
            <button @click="flipCard(3)">
              <span>En savoir plus</span>
              <span class="icon">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 448 512"
                  class="svg-icon"
                >
                  <path
                    d="M438.6 278.6c12.5-12.5 12.5-32.8 0-45.3l-160-160c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3L338.8 224 32 224c-17.7 0-32 14.3-32 32s14.3 32 32 32l306.7 0L233.4 393.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0l160-160z"
                  ></path>
                </svg>
              </span>
            </button>
          </div>
          <div class="container project-card-back">
            <div class="terminal_toolbar">
              <div class="butt">
                <button class="btn btn-color"></button>
                <button class="btn"></button>
                <button class="btn"></button>
              </div>
              <p class="user">Musée du Jouet | Chef de projet ~</p>
              <div class="add_tab">+</div>
            </div>
            <div class="terminal_body">
              <div class="terminal_prompt">
                <span class="terminal_user">@admin:</span>
                <span class="terminal_location">~</span>
                <span class="terminal_bling">$</span>
                <span class="terminal_cursor"></span>
              </div>
              <div class="terminal_output">
                <pre class="output_text">Ce site modernise le Musée du Jouet de Poissy en permettant aux visiteurs de créer leur mascotte, projet dirigé avec une équipe de 10 personnes (designeurs, développeurs, marketeurs) et réalisé en 8 semaines dans le cadre de la Bourse au Projet de l'IIM Digital School.</pre>
              </div>
              <div class="terminal_input">
                <input placeholder="Type a command..." class="input_text" type="text" />
                <button @click="flipCard(3)">Voir moins <<</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
/* Card terminal */
/* From Uiverse.io by 00Kubi */ 
.container {
  width: 100%;
  height: auto;
  background: #1e1e1e;
  font-family: Menlo, Consolas, monospace;
  font-size: 14px;
  color: #e6e6e6;
  border-radius: 5px;
  overflow: hidden;
}
.terminal_toolbar {
  display: flex;
  height: 30px;
  align-items: center;
  padding: 0 8px;
  box-sizing: border-box;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  background: #212121;
  justify-content: space-between;
}
.butt {
  display: flex;
  align-items: center;
}
.btn {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0;
  margin-right: 5px;
  font-size: 8px;
  height: 12px;
  width: 12px;
  box-sizing: border-box;
  border: none;
  border-radius: 100%;
  background: linear-gradient(#7d7871 0%, #595953 100%);
  text-shadow: 0px 1px 0px rgba(255, 255, 255, 0.2);
  box-shadow: 0px 0px 1px 0px #41403a, 0px 1px 1px 0px #474642;
}
.btn-color {
  background: #ee411a;
}
.btn:hover {
  cursor: pointer;
}
.btn:focus {
  outline: none;
}
.butt--exit {
  background: linear-gradient(#f37458 0%, #de4c12 100%);
}
.add_tab {
  border: 1px solid #fff;
  color: #fff;
  padding: 0 6px;
  border-radius: 4px 4px 0 0;
  border-bottom: none;
  cursor: pointer;
}
.user {
  color: #d5d0ce;
  margin-left: 6px;
  font-size: 1.3rem !important;
  text-align: center;
  line-height: 20px;
  margin-bottom: 10px;
}
.terminal_body {
  background: rgba(0, 0, 0, 0.6);
  width: 100%;
  height: 210px;
  padding-top: 2px;
  margin-top: 2px;
  font-size: 12px;
  border-bottom-left-radius: 5px;
  border-bottom-right-radius: 5px;
  display: flex;
  flex-direction: column;
  overflow: hidden;
}
.terminal_prompt {
  display: flex;
  align-items: center;
  padding: 4px;
}
.terminal_prompt span {
  margin-left: 4px;
}
.terminal_user {
  color: #1eff8e;
}
.terminal_location {
  color: #4878c0;
}
.terminal_bling {
  color: #dddddd;
}
.terminal_cursor {
  display: block;
  height: 14px;
  width: 5px;
  margin-left: 10px;
  animation: curbl 1200ms linear infinite;
}
.terminal_output {
  padding: 4px;
  flex-grow: 1;
  overflow-y: auto;
}
.output_text {
  margin: 0;
  color: rgb(255, 255, 255);
  text-wrap: balance;
}
.terminal_input {
  padding: 4px;
}
.input_text {
  width: 100%;
  padding: 6px;
  background: transparent;
  border: none;
  color: #ffffff;
  caret-color: #1eff8e;
}

@keyframes curbl {
  0% {
    background: #ffffff;
  }

  49% {
    background: #ffffff;
  }

  60% {
    background: transparent;
  }

  99% {
    background: transparent;
  }

  100% {
    background: #ffffff;
  }
}
/* Card terminal */






/* button */
/* From Uiverse.io by tomaskriegelstein */ 
button {
  font-size: 1.2rem;
  margin-top: 10px;
  font-weight: 700;
  color: grey;
  cursor: pointer;
  position: relative;
  border: none;
  background: none;
  transition-timing-function: cubic-bezier(0.25, 0.8, 0.25, 1);
  transition-duration: 400ms;
  transition-property: color;
  display: inline-flex;
  align-items: center;
}

button:focus,
button:hover {
  color: white;
}

button:focus:after,
button:hover:after {
  width: 100%;
  left: auto; /* Ensure left is auto to override the initial value */
}

button:after {
  content: "";
  pointer-events: none;
  bottom: -7px;
  right: auto; /* Start from the right */
  left: 0; /* Ensure left is auto to override the initial value */
  position: absolute;
  width: 0%;
  height: 1px;
  background-color: #fff;
  transition-timing-function: cubic-bezier(0.25, 0.8, 0.25, 1);
  transition-duration: 500ms;
  transition-property: width, right;
}

.svg-icon {
  width: 0.9em;
  height: 0.8em;
  margin-left: 10px;
  fill: grey;
  transform: rotate(-45deg);
  transition: transform 0.5s ease-out;
}

button:hover .svg-icon {
  transform: rotate(0deg);
  fill: white;
}






/* button */

.project-title {
  margin-top: 0;
  color: #f0f0f0;
  font-size: 1.5rem;
  font-weight: 500;
  text-align: center;
}

.body {
    background-color: #000;
    color: #fff;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px; /* Ajoute du padding pour respirer */
    overflow: hidden;
}
.body h2 {
    font-size: 2rem;
    margin-top: 50px;
}
.body p {
    font-size: 1.5rem;
    text-align: center;
}
.projects-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
  margin-top: 20px;
  width: 100%; /* Utilise toute la largeur disponible */
  height: 70vh;
  min-height: 70vh;
}

@media screen and (max-width: 1400px) {
  .projects-container {
    height: 130vh;
  }
}
@media screen and (max-width: 768px) {
  .projects-container {
    height: 160vh;
  }
  
}

.project-card {
  perspective: 1000px; /* Ajoute de la perspective pour l'effet 3D */
  width: 90%; /* Utilise un pourcentage pour une largeur flexible */
  max-width: 300px; /* Limite la taille maximale de la carte */
  height: auto; /* Hauteur automatique pour s'adapter au contenu */
}

.project-card-inner {
  position: relative;
  width: 100%;
  height: 0; /* Hauteur initiale nulle, remplie par le padding-top */
  transition: transform 0.6s;
  transform-style: preserve-3d; /* Assure l'effet 3D */
}

.project-card.flipped .project-card-inner {
  transform: rotateY(180deg); /* Rotation pour l'effet de flip */
}

.project-card-front,
.project-card-back {
  position: absolute;
  width: 100%;
  height: auto;
  backface-visibility: hidden; /* Masque la face arrière quand non visible */
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  color: #000;
  border-radius: 8px;
}

/* Classe pour masquer le recto de la carte */
.hide-front {
  opacity: 0; /* Masque visuellement le recto */
  visibility: hidden; /* Cache complètement le recto */
}

.project-card-front img {
  width: 100%;
  min-width: 400px;
  aspect-ratio: 16/9; /* Ratio 16:9 pour l'image */
  border-radius: 10px;
  filter: grayscale(90%); /* Image en noir et blanc */
  transition: filter 0.6s; /* Transition pour l'effet de couleur */
}

/* Ajoute une classe pour l'animation en boucle */
.project-card-front img.color-animation {
  animation: grayscaleToColor 3s infinite; /* Animation infinie avec une durée de 3s */
}

/* Animation keyframes pour passer du noir et blanc à la couleur */
@keyframes grayscaleToColor {
  0%, 100% {
    filter: grayscale(90%); /* Début et fin en noir et blanc */
  }
  50% {
    filter: grayscale(0%); /* Milieu de l'animation en couleur */
  }
}

.project-card-front img:hover {
  filter: grayscale(0%); /* Image en couleur au survol */
}

.project-card-back {
  transform: rotateY(180deg); /* Inverse la face arrière */
  width: 500px;
  min-width: 400px;
}
@media screen and (max-width: 768px) {
  .project-card-back {
    width: 100%;
    margin-left: -45px;
    margin-top: 20px;
  }
  
}

@media (min-width: 768px) {
  .projects-container {
    gap: 30px; /* Augmente l'espace entre les cartes pour les écrans plus larges */
  }
  .project-card {
    width: 45%; /* Deux cartes par rangée */
    max-width: none; /* Enlève la limite pour les écrans larges */
  }
}

@media (min-width: 1024px) {
  .project-card {
    width: 30%; /* Trois cartes par rangée sur les très grands écrans */
  }
}
</style>
