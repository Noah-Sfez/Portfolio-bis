<script>
export default {
  name: 'Timeline',
  data() {
    return {
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
};
</script>
<template>
   <div class="experience-container" @mousemove="handleMouseMove" @mouseleave="handleMouseLeave">
    <div class="mouse-shadow" :style="{left: mouseX + 'px', top: mouseY + 'px', opacity: isShadowVisible ? 0.5 : 0 }"></div>
        <div class="experience-title">
            <h1>Expériences</h1>
            <h2>Pousser les limites de la technologie.</h2>
        </div>
        <RouterLink to="/experience">Voir le détail des expériences ></RouterLink>
        <div class="timeline">
            <div class="outer">
                <div class="card" >
                <div class="info" data-aos="fade-left"
                data-aos-anchor="#example-anchor"
                data-aos-offset="1200"
                data-aos-duration="1500"
                data-aos-easing="ease-in-sine">
                    <h3 class="title">Kermony Office | Back-end</h3>
                    <h4>Décembre 2024 - Aujourd'hui</h4>
                    <p>Réalisation d'une interface pour les employés de Kermony leur permettant d'enregistrer pour chacun des clients des informations sur leur santé financière. Avec ces informations ils peuvent générer des pdf dynamique pour les clients avec des speedmeter ainsi que de profiter d'une api leur permettant de transmettre les données à leur application web.</p>
                </div>
                </div>
                <div class="card">
                <div class="info" data-aos="fade-right"
                data-aos-anchor="#example-anchor"
                data-aos-offset="1200"
                data-aos-duration="1500"
                data-aos-easing="ease-in-sine">
                    <h3 class="title">Musée du Jouet | Chef de Projet</h3>
                    <h4 class="title-h4">Octobre- Décembre 2023</h4>
                    <p>Lors de la Bourse au Projet de mon école, j'ai été choisi comme chef de projet pour réaliser une application web permettant aux visiteurs du Musée du Jouet de Poissy de créer leur propre mascotte à l'occasion des Jeux Olympiques 2024. J'ai donc du gérer une équipe de 10 personnes, comprenant des développeurs, des designers ainsi que étudiants en marketing, tous provenant de mon école. C'était l'occasion pour moi d'apprendre à rédiger un cahier des charges ainsi que de planifier des réunions clients.</p>
                </div>
                </div>
                <div class="card">
                <div class="info" data-aos="fade-left"
                data-aos-anchor="#example-anchor"
                data-aos-offset="1200"
                data-aos-duration="2500"
                data-aos-easing="ease-in-sine">
                    <h3 class="title">Nosa Coach Front-end</h3>
                    <h4>Juillet 2023</h4>
                    <p>J'ai pu réaliser un site vitrine pour une conseillère en image. L'enjeu était d'avoir un site agréable en réunissant toutes les informations nécessaires de manière synthétique. J'ai donc dû réaliser une maquette sur Figma, la faire valider à la cliente pour enfin intégrer cette maquette en HTML, CSS et Javascript.</p>
                </div>
                </div>
                <div class="card">
                <div class="info" data-aos="fade-right"
                data-aos-anchor="#example-anchor"
                data-aos-offset="1800"
                data-aos-duration="2000"
                data-aos-easing="ease-in-sine">
                    <h3 class="title">Stage chez Flowerbox</h3>
                    <h4 class="title-h4">Décembre 2018</h4>
                    <p>Lors de ce stage, j'ai eu l'occasion de pouvoir observer le fonctionnement d'une entreprise avec un site e-commerce. J'ai participé à plusieurs réunions en anglais avec des partenaires à Londres, et j'ai également pu observer la préparation des commandes et voir comment cela fonctionnait sur leur site web.</p>
                </div>
                </div>
            </div>
        </div>
</div>
</template>
<style scoped>
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
  z-index: 1000; /* Ajouté pour s'assurer qu'il est au-dessus des autres éléments */
}

.experience-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: black;
  position: relative;
}
.experience-title {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-top: 5rem;
  color: white;
}
.title-h4 {
    color: white;
    position: relative;
    left: 160px;
}
h4 {
  color: white;
}
a {
  text-decoration: none;
  color: var(--vt-c-blue-dark);
}
* {
  margin: 0;
  padding: 0;
}
body {
  background: var(--background-color);
  font-family: var(--font);
  display: flex;
  justify-content: center;
}
.timeline {
  background: var(--primary-color);
  margin: 20px auto;
  padding: 20px;
}
.card {
  position: relative;
  max-width: 400px;
}
.card:nth-child(odd) {
  padding: 30px 0 30px 30px;
}
.card:nth-child(even) {
  padding: 30px 30px 30px 0;
}
.card::before {
  content: "";
  position: absolute;
  width: 50%;
  border: solid rgb(255, 255, 255);
}
.card:nth-child(odd)::before {
  left: 0px;
  top: -4.5px;
  bottom: -4.5px;
  border-width: 5px 0 5px 5px;
  border-radius: 50px 0 0 50px;
}
@media only screen and (max-width: 400px) {
  .card:nth-child(odd)::before {
    top: -5px;
    bottom: -5px;
  }
}
.card:nth-child(even)::before {
  right: 0;
  top: 0;
  bottom: 0;
  border-width: 5px 5px 5px 0;
  border-radius: 0 50px 50px 0;
}
.card:first-child::before {
  border-top: 0;
  border-top-left-radius: 0;
}
.card:last-child:nth-child(odd)::before {
  border-bottom: 0;
  border-bottom-left-radius: 0;
}
.card:last-child:nth-child(even)::before {
  border-bottom: 0;
  border-bottom-right-radius: 0;
}
.info {
  display: flex;
  flex-direction: column;
  background: #333;
  color: gray;
  border-radius: 10px;
  padding: 10px;
}
.title {
  color: rgb(255, 255, 255);
  position: relative;
}
.title::before {
  content: "";
  position: absolute;
  width: 30px;
  height: 30px;
  background: white;
  border-radius: 999px;
  border: 5px solid rgb(0, 0, 0);
}
.card:nth-child(even) > .info > .title {
  text-align: right;
}
.card:nth-child(odd) > .info > .title::before {
  left: -52px;
}
.card:nth-child(even) > .info > .title::before {
  right: -52px;
}


@media screen and (max-width: 600px){
  .experience-title {
    margin-top: 2rem;
    font-size: 0.8rem;
  }
  h2 {
    text-align: center;
  }
  h3 {
    font-size: 1rem;
  }
  p {
    font-size: 0.8rem;
  }
  .timeline {
    padding: 30px;
  }
  .title-h4 {
    left: 0;
  }
  h4 {
    margin-bottom: 10px;
  }
}
</style>