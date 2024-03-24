<script>
import Form from '../components/Form.vue';

export default {
  components: {
    Form
  }
};


</script>


<template>
<Form style="margin-top: 60px;"/>

<div class="cv">
<h2>Télécharger mon CV.</h2>
<button class="button">
    <a href="../../public/CV-Noah-Sfez-Alternance.pdf" download="CV_Noah-SFEZ.pdf">

        <p class="text">
  Download 
  </p>
  <div class="svg">
    <svg xmlns="http://www.w3.org/2000/svg" fill="white" class="bi bi-download" viewBox="0 0 16 16"> <path d="M.5 9.9a.5.5 0 0 1 .5.5v2.5a1 1 0 0 0 1 1h12a1 1 0 0 0 1-1v-2.5a.5.5 0 0 1 1 0v2.5a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2v-2.5a.5.5 0 0 1 .5-.5z"></path> <path d="M7.646 11.854a.5.5 0 0 0 .708 0l3-3a.5.5 0 0 0-.708-.708L8.5 10.293V1.5a.5.5 0 0 0-1 0v8.793L5.354 8.146a.5.5 0 1 0-.708.708l3 3z"></path> </svg>
  </div>
    </a>
  
</button>
</div>


</template>

<style scoped>
.cv {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1rem;
    margin: 4rem 0;
    flex-direction: column;
    
}



.button {
  padding: 0.8rem 4rem;
  border: none;
  outline: none;
  font-size: 1.3rem;
  border-radius: 0.3rem;
  font-weight: 600;
  background-color: rgb(0, 102, 204);
  position: relative;
  overflow: hidden;
  cursor: pointer;
  transition: 0.4s ease-in-out;
  border: 3px solid  rgb(0, 102, 204);
}

.button .text {
  position: absolute;
  left: 1.8rem;
  top: 1.3rem;
  transition: 0.4s ease-in-out;
  color: white;
}

.svg {
  transform: translateY(-20px) rotate(30deg);
  opacity: 0;
  width: 2rem;
  transition: 0.4s ease-in-out;
}

.button:hover {
  background-color: white;
}

.button:hover .svg {
  display: inline-block;
  transform: translateY(0px) rotate(0deg);
  opacity: 1;
}

.button:hover .text {
  opacity: 0;
}

.button:active {
  scale: 0.97;
}
</style>