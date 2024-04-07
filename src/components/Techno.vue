<script>
import Social from '../components/Social.vue';

export default {
  components: {
    Social
  },
  name: 'PresentationComponent',
  data() {
    return {
      technologiesCategories: {
        'Front-end': ['HTML', 'CSS / SCSS', 'JavaScript', 'Vue.js', 'Bootsrap'],
        'Back-end': ['Node.js', 'PHP', 'MySQL'],
        'Outils & Autres': ['Git', 'NPM'], 
        'CMS': ['WordPress'],
      },
      mouseX: 0,
      mouseY: 0,
      isShadowVisible: false,
    };
  },
  methods: {
    handleMouseMove(event) {
      const containerRect = this.$el.getBoundingClientRect();
      this.mouseX = event.clientX - containerRect.left;
      this.mouseY = event.clientY - containerRect.top;
      this.isShadowVisible = true;
    },
    handleMouseLeave() {
      this.isShadowVisible = false;
    }
  }
}
</script>


<template>
  <div class="presentation-container">
    <div class="mouse-shadow" :style="{left: mouseX + 'px', top: mouseY + 'px', opacity: isShadowVisible ? 0.5 : 0 }"></div>
    <img src="../assets/images/Photo-CV(2).png" alt="Photo de Profil" title="Noah Sfez">
    <div class="text-container">
        <p>Bienvenue sur mon portfolio. Je suis un développeur web passionné par la création de solutions digitales élégantes et efficaces. Voici quelques-unes des technologies avec lesquelles j'aime travailler, classées par catégorie :</p>
        <div class="technologies-container">
          <div class="technologies-column" v-for="(techList, category) in technologiesCategories" :key="category">
            <h2>{{ category }}</h2>
            <ul>
              <li v-for="tech in techList" :key="tech">{{ tech }}</li>
            </ul>
          </div>
        </div>
        <Social class="social"/>
    </div>
  </div>
</template>



<style scoped>
.social {
  margin-top: 20px;
}

p {
  font-size: 1.2rem;
  margin-bottom: 20px;
  width: 80%;
  line-height: 3;
}


.mouse-shadow {
  position: absolute;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background-color: white;
  opacity: 0.5;
  pointer-events: none;
  transform: translate(-50%, -50%);
  filter: blur(8px);
  transition: transform 0.2s, opacity 0.2s;
  z-index: 1000; 
}



.presentation-container {
  text-align: center;
  padding: 5% 10%;
  height: auto; /* Adjusted to auto for dynamic height */
  background-color: black;
  display: flex;
  align-items: center; /* Center items horizontally */
}

.text-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.presentation-container img {
  border-radius: 50%;
  width: 250px;
  height: 250px;
  aspect-ratio: 1/1;
  margin: 20px 0;
  border: 5px solid var(--vt-c-white-light);
}

.presentation-container img:hover {
  box-shadow: 0 0 150px 5px var(--vt-c-white-light);
  transition: box-shadow 0.5s;
}

p {
  color: var(--vt-c-white-light);
}

.technologies-container {
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap; /* Added to ensure responsiveness */
}

.technologies-column h2 {
  color: var(--vt-c-white-light); /* Ensure visibility against the black background */
  margin-bottom: 10px;
}

.technologies-column ul {
  list-style-type: none;
  padding: 0;
}

.technologies-column li {
  background-color: #f0f0f0;
  color: #333;
  margin-bottom: 5px;
  padding: 5px;
  border-radius: 5px;
}

@media screen and (max-width: 768px) {
  .presentation-container {
    padding: 5% 5%;
    display: flex;
    flex-direction: column;
  }

  .text-container {
    width: 100%;
  }

  p {
    width: 100%;
    line-height: 1.8;
  }

  .technologies-container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }
}

</style>
