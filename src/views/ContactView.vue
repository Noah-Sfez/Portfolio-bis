<script>
import Form from '../components/Form.vue';
import Card from '../components/Card.vue';
export default {
  components: {
    Form, 
    Card
  },
  data() {
    return {
      isModalOpen: false, // État initial du modal, caché
    }
  },
  methods: {
    toggleModal() {
      this.isModalOpen = !this.isModalOpen; // Bascule l'état du modal
    }
  }
};
</script>
<template>
<div class="contact">
  <!--
  <Form style="margin-top: 60px;"/>
  -->
  <Card data-aos="fade-right"
     data-aos-offset="300" data-aos-duration="1000" />
  <div class="cv">
    <h2>Télécharger mon CV.</h2>
    <div style="display: flex;">
      <img src="../assets/images/cv.png" class="cv-img" data-aos="zoom-out" data-aos-duration="1000" data-aos-offset="200" alt="" @click="toggleModal">
    </div>
    <a href="../../public/CV-Noah-Sfez.pdf" download="CV-Noah-Sfez.pdf">

      <button class="botao">
        <svg
          class="mysvg"
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          height="24px"
          width="24px"
          >
            <g stroke-width="0" id="SVGRepo_bgCarrier"></g>
            <g
              stroke-linejoin="round"
              stroke-linecap="round"
              id="SVGRepo_tracerCarrier"
            ></g>
            <g id="SVGRepo_iconCarrier">
              <g id="Interface / Download">
                <path
                  stroke-linejoin="round"
                  stroke-linecap="round"
                  stroke-width="2"
                  stroke="#f1f1f1"
                  d="M6 21H18M12 3V17M12 17L17 12M12 17L7 12"
                  id="Vector"
                ></path>
              </g>
            </g>
          </svg>
          <span class="texto">Download</span>
      </button>
    </a>
    

  </div>

  <!-- Modal Structure -->
  <div v-if="isModalOpen" class="modal" @click.self="toggleModal">
    <div class="modal-content">
      <img src="../assets/images/cv.png" class="modal-cv-img" alt="">
    </div>
  </div>
</div>
  
</template>

<style scoped>
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-content {
  background: white;
  padding: 10px;
}

.modal-cv-img {
  width: 100%;
  max-width: 550px; /* Adapte cette taille à tes besoins */
}



.contact {
  display: flex;
  align-items: center;
  gap: 2rem;
  margin-top: 60px;
  justify-content: center;
}
.cv {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1rem;
    margin: 4rem 0;
    flex-direction: column;
    
}
.cv-img {
    margin: 20px;
    width: 300px;
    height: auto;
    cursor: pointer;
    transition: 0.4s ease-in-out;
}
.cv-img:hover {
    transform: scale(1.1);
}


.botao {
  width: 125px;
  height: 45px;
  border-radius: 20px;
  border: none;
  box-shadow: 1px 1px rgba(107, 221, 215, 0.37);
  padding: 5px 10px;
  background-color: var(--vt-c-blue-light);
  color: #fff;
  font-family: Roboto, sans-serif;
  font-weight: 505;
  font-size: 16px;
  line-height: 1;
  cursor: pointer;
  filter: drop-shadow(0 0 10px rgba(59, 190, 230, 0.568));
  transition: 0.5s linear;
}

.botao .mysvg {
  display: none;
}

.botao:hover {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  transition: 0.5s linear;
}

.botao:hover .texto {
  display: none;
}

.botao:hover .mysvg {
  display: inline;
}

.botao:hover::after {
  content: "";
  position: absolute;
  width: 16px;
  height: 3px;
  background-color: var(--vt-c-blue-light);
  margin-left: -20px;
  animation: animate 0.9s linear infinite;
}

.botao:hover::before {
  content: "";
  position: absolute;
  top: -3px;
  left: -3px;
  width: 100%;
  height: 100%;
  border: 3.5px solid transparent;
  border-top: 3.5px solid #fff;
  border-right: 3.5px solid #fff;
  border-radius: 50%;
  animation: animateC 2s linear infinite;
}

@keyframes animateC {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(360deg);
  }
}

@keyframes animate {
  0% {
    transform: translateY(0);
  }

  100% {
    transform: translateY(20px);
  }
}


@media screen and (max-width: 768px) {
  .contact {
    flex-direction: column;
    margin: 0;
  }
  .cv {
    margin: 0 0 2rem 0;
  }
  .cv-img {
    width: 200px;
  }
  .modal-cv-img {
    width: 100%;
    max-width: 350px; /* Adapte cette taille à tes besoins */
  }
}



</style>