<template>
    <form @submit.prevent="submitForm">
        <h2>Me contacter.</h2>
        <div class="names">
            <div class="form-control">
            <input type="text" v-model="prenom" required>
            <label>
                <span style="transition-delay:0ms">P</span><span style="transition-delay:50ms">r</span><span style="transition-delay:100ms">é</span><span style="transition-delay:150ms">n</span><span style="transition-delay:200ms">o</span><span style="transition-delay:250ms">m</span>
            </label>
        </div>
        <div class="form-control">
            <input type="text" v-model="nom" required>
            <label>
                <span style="transition-delay:0ms">N</span><span style="transition-delay:50ms">o</span><span style="transition-delay:100ms">m</span>
            </label>
        </div>
        </div>
        <div class="form-control">
            <input type="email" v-model="email" required class="mail">
            <label>
                <span style="transition-delay:0ms">E</span><span style="transition-delay:50ms">m</span><span style="transition-delay:100ms">a</span><span style="transition-delay:150ms">i</span><span style="transition-delay:200ms">l</span>
            </label>
        </div>
        <textarea v-model="message" cols="30" rows="10" placeholder="Votre message ..." required></textarea>
        <button type="submit">
            <div class="svg-wrapper-1">
                <div class="svg-wrapper">
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 24 24"
                    width="24"
                    height="24"
                >
                    <path fill="none" d="M0 0h24v24H0z"></path>
                    <path
                    fill="currentColor"
                    d="M1.946 9.315c-.522-.174-.527-.455.01-.634l19.087-6.362c.529-.176.832.12.684.638l-5.454 19.086c-.15.529-.455.547-.679.045L12 14l6-8-8 6-8.054-2.685z"
                    ></path>
                </svg>
                </div>
            </div>
            <span>Send</span>
        </button>
    </form>

</template>
<script>
import emailjs from 'emailjs-com';

export default {
  name: 'ContactForm',
  data() {
    return {
      prenom: '',
      nom: '',
      email: '',
      message: '',
    };
  },
  mounted() {
    emailjs.init("TGsDSOgRYW18klcrq"); // Remplace par ton User ID réel
  },
  methods: {
  submitForm() {
    emailjs.send("service_76ykyxl", "template_efxsu0o", {
      // les paramètres de ton template
      from_name: this.prenom + ' ' + this.nom,
      reply_to: this.email,
      message: this.message,
      // Assure-toi d'avoir ces noms de paramètre correspondant à ceux de ton template EmailJS
    }, "ton-secure-token") // Remplace 'ton-secure-token' par ton SecureToken réel
    .then(
      (response) => {
        console.log('SUCCESS!', response.status, response.text);
        alert('Votre message a été envoyé avec succès !');
        this.resetForm();
      }, 
      (error) => {
        console.error('FAILED...', error);
        alert('Une erreur s\'est produite lors de l\'envoi du message.');
      }
    );
  },
  resetForm() {
    this.prenom = '';
    this.nom = '';
    this.email = '';
    this.message = '';
  }
}
}
</script>
<style scoped>
button {
    margin: 20px 0px;
  font-family: inherit;
  font-size: 20px;
  background: var(--vt-c-blue-light);
  color: var(--vt-c-white-light);
  padding: 0.7em 1em;
  padding-left: 0.9em;
  display: flex;
  align-items: center;
  border: none;
  border-radius: 16px;
  overflow: hidden;
  transition: all 0.2s;
  cursor: pointer;
}

button span {
  display: block;
  margin-left: 0.3em;
  transition: all 0.3s ease-in-out;
}

button svg {
  display: block;
  transform-origin: center center;
  transition: transform 0.3s ease-in-out;
}

button:hover .svg-wrapper {
  animation: fly-1 0.6s ease-in-out infinite alternate;
}

button:hover svg {
  transform: translateX(1.2em) rotate(45deg) scale(1.1);
}

button:hover span {
  transform: translateX(5em);
}

button:active {
  transform: scale(0.95);
}

@keyframes fly-1 {
  from {
    transform: translateY(0.1em);
  }

  to {
    transform: translateY(-0.1em);
  }
}

.mail {
    width: 120% !important;

}
form {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5%;
}
.names {
    display: flex;
    gap: 5%;
}
.form-control {
  position: relative;
  margin: 20px 0 40px;
  width: 190px;
}
.form-control input {
  background-color: transparent;
  border: 0;
  border-bottom: 2px #000000 solid;
  display: block;
  width: 100%;
  padding: 15px 0;
  font-size: 18px;
  color: #000000;
}
.form-control input:focus,
.form-control input:valid {
  outline: 0;
  border-bottom-color: rgb(0, 0, 0);
}
.form-control label {
  position: absolute;
  top: 15px;
  left: 0;
  pointer-events: none;
}
.form-control label span {
  display: inline-block;
  font-size: 18px;
  min-width: 5px;
  color: #000000;
  transition: 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55);
}
.form-control input:focus+label span,
.form-control input:valid+label span {
  color: rgb(0, 0, 0);
  transform: translateY(-30px);
}

textarea {
  width: 40%;
  height: 180px;
  padding: 10px;
  font-size: 1rem;
  border: 2px solid #000000;
  border-radius: 5px;
  resize: none;
  font-family: Arial, Helvetica, sans-serif;
}

@media screen and (max-width: 768px) {
  form {
    width: 80%;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5%;
    margin: 20px auto;
  }
  textarea {
    width: 100%;
  }
  .names {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 120%;
    gap: 5%;
  }
  input {
    width: 120%;
  }
  .mail {
    width: 100% !important;
  }
}
</style>