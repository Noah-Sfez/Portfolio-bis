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

window.addEventListener("load", () => {
    const logos = document.querySelectorAll('.logo');
    const logoColors = {
        "html-logo": "#E34F26",
        "css-logo": "#1572B6",
        "js-logo": "#F7DF1E",
        "php-logo": "#777BB4",
        "wordpress-logo": "#21759B",
        "node-logo": "#339933",
        "mysql-logo": "#4479A1",
        "vue-logo": "#4FC08D",
        "python-logo": "#3776AB",
        "git-logo": "#F05032",
        "sass-logo": "#CC6699"
    };
    
    function getRandomInt(min, max) {
        return Math.floor(Math.random() * (max - min + 1)) + min;
    }

    function applyRandomColor() {
        // Reset all logos to grayscale
        logos.forEach(logo => {
            logo.classList.remove('colored');
            logo.querySelector('svg').style.fill = '';
        });

        // Select a random logo
        const randomIndex = getRandomInt(0, logos.length - 1);
        const randomLogo = logos[randomIndex];
        const logoId = randomLogo.getAttribute("id");
        
        // Apply specific color to the selected logo
        randomLogo.classList.add('colored');
        randomLogo.querySelector('svg').style.fill = logoColors[logoId];
    }

    setInterval(applyRandomColor, 1000); // Change color every second
});






</script>
<template>
  <main>
    <!-------------------------------- Presentation ---------------------------->
    <div class="background">
        <div class="logo" id="html-logo">
            <!-- Insère ici le code SVG pour le logo HTML -->
             <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>HTML5</title><path d="M1.5 0h21l-1.91 21.563L11.977 24l-8.564-2.438L1.5 0zm7.031 9.75l-.232-2.718 10.059.003.23-2.622L5.412 4.41l.698 8.01h9.126l-.326 3.426-2.91.804-2.955-.81-.188-2.11H6.248l.33 4.171L12 19.351l5.379-1.443.744-8.157H8.531z"/></svg>
        </div>
        <div class="logo" id="css-logo">
            <!-- Insère ici le code SVG pour le logo CSS -->
             <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>CSS3</title><path d="M1.5 0h21l-1.91 21.563L11.977 24l-8.565-2.438L1.5 0zm17.09 4.413L5.41 4.41l.213 2.622 10.125.002-.255 2.716h-6.64l.24 2.573h6.182l-.366 3.523-2.91.804-2.956-.81-.188-2.11h-2.61l.29 3.855L12 19.288l5.373-1.53L18.59 4.414z"/></svg>
        </div>
        <div class="logo" id="js-logo">
            <!-- Insère ici le code SVG pour le logo JavaScript -->
             <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>JavaScript</title><path d="M0 0h24v24H0V0zm22.034 18.276c-.175-1.095-.888-2.015-3.003-2.873-.736-.345-1.554-.585-1.797-1.14-.091-.33-.105-.51-.046-.705.15-.646.915-.84 1.515-.66.39.12.75.42.976.9 1.034-.676 1.034-.676 1.755-1.125-.27-.42-.404-.601-.586-.78-.63-.705-1.469-1.065-2.834-1.034l-.705.089c-.676.165-1.32.525-1.71 1.005-1.14 1.291-.811 3.541.569 4.471 1.365 1.02 3.361 1.244 3.616 2.205.24 1.17-.87 1.545-1.966 1.41-.811-.18-1.26-.586-1.755-1.336l-1.83 1.051c.21.48.45.689.81 1.109 1.74 1.756 6.09 1.666 6.871-1.004.029-.09.24-.705.074-1.65l.046.067zm-8.983-7.245h-2.248c0 1.938-.009 3.864-.009 5.805 0 1.232.063 2.363-.138 2.711-.33.689-1.18.601-1.566.48-.396-.196-.597-.466-.83-.855-.063-.105-.11-.196-.127-.196l-1.825 1.125c.305.63.75 1.172 1.324 1.517.855.51 2.004.675 3.207.405.783-.226 1.458-.691 1.811-1.411.51-.93.402-2.07.397-3.346.012-2.054 0-4.109 0-6.179l.004-.056z"/></svg>
        </div>
        <div class="logo" id="php-logo">
            <!-- Insère ici le code SVG pour le logo PHP -->
             <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>PHP</title><path d="M7.01 10.207h-.944l-.515 2.648h.838c.556 0 .97-.105 1.242-.314.272-.21.455-.559.55-1.049.092-.47.05-.802-.124-.995-.175-.193-.523-.29-1.047-.29zM12 5.688C5.373 5.688 0 8.514 0 12s5.373 6.313 12 6.313S24 15.486 24 12c0-3.486-5.373-6.312-12-6.312zm-3.26 7.451c-.261.25-.575.438-.917.551-.336.108-.765.164-1.285.164H5.357l-.327 1.681H3.652l1.23-6.326h2.65c.797 0 1.378.209 1.744.628.366.418.476 1.002.33 1.752a2.836 2.836 0 0 1-.305.847c-.143.255-.33.49-.561.703zm4.024.715l.543-2.799c.063-.318.039-.536-.068-.651-.107-.116-.336-.174-.687-.174H11.46l-.704 3.625H9.388l1.23-6.327h1.367l-.327 1.682h1.218c.767 0 1.295.134 1.586.401s.378.7.263 1.299l-.572 2.944h-1.389zm7.597-2.265a2.782 2.782 0 0 1-.305.847c-.143.255-.33.49-.561.703a2.44 2.44 0 0 1-.917.551c-.336.108-.765.164-1.286.164h-1.18l-.327 1.682h-1.378l1.23-6.326h2.649c.797 0 1.378.209 1.744.628.366.417.477 1.001.331 1.751zM17.766 10.207h-.943l-.516 2.648h.838c.557 0 .971-.105 1.242-.314.272-.21.455-.559.551-1.049.092-.47.049-.802-.125-.995s-.524-.29-1.047-.29z"/></svg>
        </div>
        <div class="logo" id="wordpress-logo">
          <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>WordPress</title><path d="M21.469 6.825c.84 1.537 1.318 3.3 1.318 5.175 0 3.979-2.156 7.456-5.363 9.325l3.295-9.527c.615-1.54.82-2.771.82-3.864 0-.405-.026-.78-.07-1.11m-7.981.105c.647-.03 1.232-.105 1.232-.105.582-.075.514-.93-.067-.899 0 0-1.755.135-2.88.135-1.064 0-2.85-.15-2.85-.15-.585-.03-.661.855-.075.885 0 0 .54.061 1.125.09l1.68 4.605-2.37 7.08L5.354 6.9c.649-.03 1.234-.1 1.234-.1.585-.075.516-.93-.065-.896 0 0-1.746.138-2.874.138-.2 0-.438-.008-.69-.015C4.911 3.15 8.235 1.215 12 1.215c2.809 0 5.365 1.072 7.286 2.833-.046-.003-.091-.009-.141-.009-1.06 0-1.812.923-1.812 1.914 0 .89.513 1.643 1.06 2.531.411.72.89 1.643.89 2.977 0 .915-.354 1.994-.821 3.479l-1.075 3.585-3.9-11.61.001.014zM12 22.784c-1.059 0-2.081-.153-3.048-.437l3.237-9.406 3.315 9.087c.024.053.05.101.078.149-1.12.393-2.325.609-3.582.609M1.211 12c0-1.564.336-3.05.935-4.39L7.29 21.709C3.694 19.96 1.212 16.271 1.211 12M12 0C5.385 0 0 5.385 0 12s5.385 12 12 12 12-5.385 12-12S18.615 0 12 0"/></svg>
        </div>
        <div class="logo" id="node-logo">
          <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Node.js</title><path d="M11.998,24c-0.321,0-0.641-0.084-0.922-0.247l-2.936-1.737c-0.438-0.245-0.224-0.332-0.08-0.383 c0.585-0.203,0.703-0.25,1.328-0.604c0.065-0.037,0.151-0.023,0.218,0.017l2.256,1.339c0.082,0.045,0.197,0.045,0.272,0l8.795-5.076 c0.082-0.047,0.134-0.141,0.134-0.238V6.921c0-0.099-0.053-0.192-0.137-0.242l-8.791-5.072c-0.081-0.047-0.189-0.047-0.271,0 L3.075,6.68C2.99,6.729,2.936,6.825,2.936,6.921v10.15c0,0.097,0.054,0.189,0.139,0.235l2.409,1.392 c1.307,0.654,2.108-0.116,2.108-0.89V7.787c0-0.142,0.114-0.253,0.256-0.253h1.115c0.139,0,0.255,0.112,0.255,0.253v10.021 c0,1.745-0.95,2.745-2.604,2.745c-0.508,0-0.909,0-2.026-0.551L2.28,18.675c-0.57-0.329-0.922-0.945-0.922-1.604V6.921 c0-0.659,0.353-1.275,0.922-1.603l8.795-5.082c0.557-0.315,1.296-0.315,1.848,0l8.794,5.082c0.57,0.329,0.924,0.944,0.924,1.603 v10.15c0,0.659-0.354,1.273-0.924,1.604l-8.794,5.078C12.643,23.916,12.324,24,11.998,24z M19.099,13.993 c0-1.9-1.284-2.406-3.987-2.763c-2.731-0.361-3.009-0.548-3.009-1.187c0-0.528,0.235-1.233,2.258-1.233 c1.807,0,2.473,0.389,2.747,1.607c0.024,0.115,0.129,0.199,0.247,0.199h1.141c0.071,0,0.138-0.031,0.186-0.081 c0.048-0.054,0.074-0.123,0.067-0.196c-0.177-2.098-1.571-3.076-4.388-3.076c-2.508,0-4.004,1.058-4.004,2.833 c0,1.925,1.488,2.457,3.895,2.695c2.88,0.282,3.103,0.703,3.103,1.269c0,0.983-0.789,1.402-2.642,1.402 c-2.327,0-2.839-0.584-3.011-1.742c-0.02-0.124-0.126-0.215-0.253-0.215h-1.137c-0.141,0-0.254,0.112-0.254,0.253 c0,1.482,0.806,3.248,4.655,3.248C17.501,17.007,19.099,15.91,19.099,13.993z"/></svg>        
        </div>
        <div class="logo" id="mysql-logo">
          <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>MySQL</title><path d="M16.405 5.501c-.115 0-.193.014-.274.033v.013h.014c.054.104.146.18.214.273.054.107.1.214.154.32l.014-.015c.094-.066.14-.172.14-.333-.04-.047-.046-.094-.08-.14-.04-.067-.126-.1-.18-.153zM5.77 18.695h-.927a50.854 50.854 0 00-.27-4.41h-.008l-1.41 4.41H2.45l-1.4-4.41h-.01a72.892 72.892 0 00-.195 4.41H0c.055-1.966.192-3.81.41-5.53h1.15l1.335 4.064h.008l1.347-4.064h1.095c.242 2.015.384 3.86.428 5.53zm4.017-4.08c-.378 2.045-.876 3.533-1.492 4.46-.482.716-1.01 1.073-1.583 1.073-.153 0-.34-.046-.566-.138v-.494c.11.017.24.026.386.026.268 0 .483-.075.647-.222.197-.18.295-.382.295-.605 0-.155-.077-.47-.23-.944L6.23 14.615h.91l.727 2.36c.164.536.233.91.205 1.123.4-1.064.678-2.227.835-3.483zm12.325 4.08h-2.63v-5.53h.885v4.85h1.745zm-3.32.135l-1.016-.5c.09-.076.177-.158.255-.25.433-.506.648-1.258.648-2.253 0-1.83-.718-2.746-2.155-2.746-.704 0-1.254.232-1.65.697-.43.508-.646 1.256-.646 2.245 0 .972.19 1.686.574 2.14.35.41.877.615 1.583.615.264 0 .506-.033.725-.098l1.325.772.36-.622zM15.5 17.588c-.225-.36-.337-.94-.337-1.736 0-1.393.424-2.09 1.27-2.09.443 0 .77.167.977.5.224.362.336.936.336 1.723 0 1.404-.424 2.108-1.27 2.108-.445 0-.77-.167-.978-.5zm-1.658-.425c0 .47-.172.856-.516 1.156-.344.3-.803.45-1.384.45-.543 0-1.064-.172-1.573-.515l.237-.476c.438.22.833.328 1.19.328.332 0 .593-.073.783-.22a.754.754 0 00.3-.615c0-.33-.23-.61-.648-.845-.388-.213-1.163-.657-1.163-.657-.422-.307-.632-.636-.632-1.177 0-.45.157-.81.47-1.085.315-.278.72-.415 1.22-.415.512 0 .98.136 1.4.41l-.213.476a2.726 2.726 0 00-1.064-.23c-.283 0-.502.068-.654.206a.685.685 0 00-.248.524c0 .328.234.61.666.85.393.215 1.187.67 1.187.67.433.305.648.63.648 1.168zm9.382-5.852c-.535-.014-.95.04-1.297.188-.1.04-.26.04-.274.167.055.053.063.14.11.214.08.134.218.313.346.407.14.11.28.216.427.31.26.16.555.255.81.416.145.094.293.213.44.313.073.05.12.14.214.172v-.02c-.046-.06-.06-.147-.105-.214-.067-.067-.134-.127-.2-.193a3.223 3.223 0 00-.695-.675c-.214-.146-.682-.35-.77-.595l-.013-.014c.146-.013.32-.066.46-.106.227-.06.435-.047.67-.106.106-.027.213-.06.32-.094v-.06c-.12-.12-.21-.283-.334-.395a8.867 8.867 0 00-1.104-.823c-.21-.134-.476-.22-.697-.334-.08-.04-.214-.06-.26-.127-.12-.146-.19-.34-.275-.514a17.69 17.69 0 01-.547-1.163c-.12-.262-.193-.523-.34-.763-.69-1.137-1.437-1.826-2.586-2.5-.247-.14-.543-.2-.856-.274-.167-.008-.334-.02-.5-.027-.11-.047-.216-.174-.31-.235-.38-.24-1.364-.76-1.644-.072-.18.434.267.862.422 1.082.115.153.26.328.34.5.047.116.06.235.107.356.106.294.207.622.347.897.073.14.153.287.247.413.054.073.146.107.167.227-.094.136-.1.334-.154.5-.24.757-.146 1.693.194 2.25.107.166.362.534.703.393.3-.12.234-.5.32-.835.02-.08.007-.133.048-.187v.015c.094.188.188.367.274.555.206.328.566.668.867.895.16.12.287.328.487.402v-.02h-.015c-.043-.058-.1-.086-.154-.133a3.445 3.445 0 01-.35-.4 8.76 8.76 0 01-.747-1.218c-.11-.21-.202-.436-.29-.643-.04-.08-.04-.2-.107-.24-.1.146-.247.273-.32.453-.127.288-.14.642-.188 1.01-.027.007-.014 0-.027.014-.214-.052-.287-.274-.367-.46-.2-.475-.233-1.238-.06-1.785.047-.14.247-.582.167-.716-.042-.127-.174-.2-.247-.303a2.478 2.478 0 01-.24-.427c-.16-.374-.24-.788-.414-1.162-.08-.173-.22-.354-.334-.513-.127-.18-.267-.307-.368-.52-.033-.073-.08-.194-.027-.274.014-.054.042-.075.094-.09.088-.072.335.022.422.062.247.1.455.194.662.334.094.066.195.193.315.226h.14c.214.047.455.014.655.073.355.114.675.28.962.46a5.953 5.953 0 012.085 2.286c.08.154.115.295.188.455.14.33.313.663.455.982.14.315.275.636.476.897.1.14.502.213.682.286.133.06.34.115.46.188.23.14.454.3.67.454.11.076.443.243.463.378z"/></svg>
        </div>
        <div class="logo" id="vue-logo">
          <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Vue.js</title><path d="M24,1.61H14.06L12,5.16,9.94,1.61H0L12,22.39ZM12,14.08,5.16,2.23H9.59L12,6.41l2.41-4.18h4.43Z"/></svg>
        </div>
        <div class="logo" id="python-logo">
          <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Python</title><path d="M14.25.18l.9.2.73.26.59.3.45.32.34.34.25.34.16.33.1.3.04.26.02.2-.01.13V8.5l-.05.63-.13.55-.21.46-.26.38-.3.31-.33.25-.35.19-.35.14-.33.1-.3.07-.26.04-.21.02H8.77l-.69.05-.59.14-.5.22-.41.27-.33.32-.27.35-.2.36-.15.37-.1.35-.07.32-.04.27-.02.21v3.06H3.17l-.21-.03-.28-.07-.32-.12-.35-.18-.36-.26-.36-.36-.35-.46-.32-.59-.28-.73-.21-.88-.14-1.05-.05-1.23.06-1.22.16-1.04.24-.87.32-.71.36-.57.4-.44.42-.33.42-.24.4-.16.36-.1.32-.05.24-.01h.16l.06.01h8.16v-.83H6.18l-.01-2.75-.02-.37.05-.34.11-.31.17-.28.25-.26.31-.23.38-.2.44-.18.51-.15.58-.12.64-.1.71-.06.77-.04.84-.02 1.27.05zm-6.3 1.98l-.23.33-.08.41.08.41.23.34.33.22.41.09.41-.09.33-.22.23-.34.08-.41-.08-.41-.23-.33-.33-.22-.41-.09-.41.09zm13.09 3.95l.28.06.32.12.35.18.36.27.36.35.35.47.32.59.28.73.21.88.14 1.04.05 1.23-.06 1.23-.16 1.04-.24.86-.32.71-.36.57-.4.45-.42.33-.42.24-.4.16-.36.09-.32.05-.24.02-.16-.01h-8.22v.82h5.84l.01 2.76.02.36-.05.34-.11.31-.17.29-.25.25-.31.24-.38.2-.44.17-.51.15-.58.13-.64.09-.71.07-.77.04-.84.01-1.27-.04-1.07-.14-.9-.2-.73-.25-.59-.3-.45-.33-.34-.34-.25-.34-.16-.33-.1-.3-.04-.25-.02-.2.01-.13v-5.34l.05-.64.13-.54.21-.46.26-.38.3-.32.33-.24.35-.2.35-.14.33-.1.3-.06.26-.04.21-.02.13-.01h5.84l.69-.05.59-.14.5-.21.41-.28.33-.32.27-.35.2-.36.15-.36.1-.35.07-.32.04-.28.02-.21V6.07h2.09l.14.01zm-6.47 14.25l-.23.33-.08.41.08.41.23.33.33.23.41.08.41-.08.33-.23.23-.33.08-.41-.08-.41-.23-.33-.33-.23-.41-.08-.41.08z"/></svg>
        </div>
        <div class="logo" id="git-logo">
          <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Git</title><path d="M23.546 10.93L13.067.452c-.604-.603-1.582-.603-2.188 0L8.708 2.627l2.76 2.76c.645-.215 1.379-.07 1.889.441.516.515.658 1.258.438 1.9l2.658 2.66c.645-.223 1.387-.078 1.9.435.721.72.721 1.884 0 2.604-.719.719-1.881.719-2.6 0-.539-.541-.674-1.337-.404-1.996L12.86 8.955v6.525c.176.086.342.203.488.348.713.721.713 1.883 0 2.6-.719.721-1.889.721-2.609 0-.719-.719-.719-1.879 0-2.598.182-.18.387-.316.605-.406V8.835c-.217-.091-.424-.222-.6-.401-.545-.545-.676-1.342-.396-2.009L7.636 3.7.45 10.881c-.6.605-.6 1.584 0 2.189l10.48 10.477c.604.604 1.582.604 2.186 0l10.43-10.43c.605-.603.605-1.582 0-2.187"/></svg>
        </div>
        <div class="logo" id="sass-logo">
          <svg role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Sass</title><path d="M12 0c6.627 0 12 5.373 12 12s-5.373 12-12 12S0 18.627 0 12 5.373 0 12 0zM9.615 15.998c.175.645.156 1.248-.024 1.792l-.065.18c-.024.061-.052.12-.078.176-.14.29-.326.56-.555.81-.698.759-1.672 1.047-2.09.805-.45-.262-.226-1.335.584-2.19.871-.918 2.12-1.509 2.12-1.509v-.003l.108-.061zm9.911-10.861c-.542-2.133-4.077-2.834-7.422-1.645-1.989.707-4.144 1.818-5.693 3.267C4.568 8.48 4.275 9.98 4.396 10.607c.427 2.211 3.457 3.657 4.703 4.73v.006c-.367.18-3.056 1.529-3.686 2.925-.675 1.47.105 2.521.615 2.655 1.575.436 3.195-.36 4.065-1.649.84-1.261.766-2.881.404-3.676.496-.135 1.08-.195 1.83-.104 2.101.24 2.521 1.56 2.43 2.1-.09.539-.523.854-.674.944-.15.091-.195.12-.181.181.015.09.091.09.21.075.165-.03 1.096-.45 1.141-1.471.045-1.29-1.186-2.729-3.375-2.7-.9.016-1.471.091-1.875.256-.03-.045-.061-.075-.105-.105-1.35-1.455-3.855-2.475-3.75-4.41.03-.705.285-2.564 4.8-4.814 3.705-1.846 6.661-1.335 7.171-.21.733 1.604-1.576 4.59-5.431 5.024-1.47.165-2.235-.404-2.431-.615-.209-.225-.239-.24-.314-.194-.12.06-.045.255 0 .375.12.3.585.825 1.396 1.095.704.225 2.43.359 4.5-.45 2.324-.899 4.139-3.405 3.614-5.505l.073.067z"/></svg>
        </div>
          <!-- Ajoute autant de logos que tu veux -->
    </div>
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


body {
    margin: 0;
    padding: 0;
    background-color: white;
    font-family: Arial, sans-serif;
    position: relative;
    overflow-x: hidden;
}

.background {
    position: absolute;
    top: 10;
    left: 0;
    width: 100%;
    height: 50vh;
    z-index: 0; /* Assure que la background est derrière */
}

.logo {
    position: absolute; /* Positionnement absolu pour le placement aléatoire */
    filter: grayscale(100%);
    opacity: 0.5;
    transition: filter 0.5s, opacity 0.5s, fill 0.5s, transform 0.5s;
}
.logo.colored {
    filter: grayscale(0%);
    opacity: 1;
}

/* Positionnement aléatoire */

/* Ajoutez les positions spécifiques pour chaque logo ici */
#html-logo {
    top: 20%;
    left: 10%;
    transform: rotate(-10deg);
    width: 80px;
    height: 60px;
}

#css-logo {
    top: 20%;
    left: 70%;
    transform: rotate(20deg);
    width: 100px;
    height: 70px;
}

#js-logo {
    top: 40%;
    left: 25%;
    transform: rotate(-30deg);
    width: 80px;
    height: 65px;
}

#php-logo {
    top: 25%;
    left: 85%;
    transform: rotate(-10deg);
    width: 125px;
    height: 55px;
}

#wordpress-logo {
    top: 100%;
    left: 10%;
    transform: rotate(-15deg);
    width: 130px;
    height: 50px;
}

#node-logo {
    top: 85%;
    left: 73%;
    transform: rotate(-25deg);
    width: 115px;
    height: 75px;
}

#mysql-logo {
    top: 120%;
    left: 60%;
    transform: rotate(5deg);
    width: 120px;
    height: 120px;
}

#vue-logo {
    top: 60%;
    left: 65%;
    transform: rotate(-15deg);
    width: 95px;
    height: 65px;
}

#python-logo {
    top: 90%;
    left: 30%;
    transform: rotate(20deg);
    width: 110px;
    height: 70px;
}

#git-logo {
    top: 100%;
    left: 90%;
    transform: rotate(30deg);
    width: 90px;
    height: 60px;
}

#sass-logo {
    top: 5%;
    left: 35%;
    transform: rotate(10deg);
    width: 70px;
    height: 50px;
}

/* Fin des positions spécifiques */

.firstDiv {
    position: relative;
    z-index: 1; /* Assure que la firstDiv est devant */
    text-align: center;
    min-height: 100vh; /* Assure que la div prend au moins toute la hauteur de l'écran */
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    padding-top: 10%;
}

.underTitle {
    margin-top: 5%;
    text-align: center;
}

.title-general {
    font-size: 5rem;
    background: linear-gradient(to bottom, #ffffff, #444444); /* Dégradé vertical */
    -webkit-background-clip: text; /* Appliquer le dégradé au texte */
    color: transparent; /* Rendre le texte transparent pour voir le dégradé */
    text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5); /* Ombre portée floue */
    font-weight: bold;
    margin-bottom: 0.5rem;
}

.soustitle-general {
    text-align: center;
    font-size: 1.5rem;
    color: var(--vt-c-black-text);
    margin-bottom: 0rem;
}

a {
    text-align: center;
    font-size: 1.5rem;
    color: var(--vt-c-blue-light);
}

.imgprofil {
    width: 15.5%;
    height: auto;
    position: absolute;
    bottom: 0;
    left: 40%;
    transform: translateX(-50%);
}

@media (max-width: 768px) {
  .background {
    display: none;
  }
    .title-general {
        font-size: 2.5rem;
    }

    .soustitle-general {
        font-size: 1.5rem;
        font-weight: bold;
    }

    a {
        font-size: 1.rem;
    }

    .imgprofil {
        width: 25%;
        left: 12%;
    }
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
