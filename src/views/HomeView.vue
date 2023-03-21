<template>
  <!--HEADER-->
  <div id="home" class="home">
    <!--Navbar + Header Banner-->
    <NavbarVue />
    <HdrBannerVue />

    <div class="row home-title">
      <h1 id="animate_text" class="">Développeur web Junior</h1>

      <h2><a href="#about" class="HS-link">Découvrir qui je suis ...</a></h2>
    </div>
  </div>

  <!--About Container-->
  <About/>
  <!--Education Container-->
  <EducationVue />
  <!--Web Projects Container-->
  <WebProjectsVue />
  <!--Footer-->
  <FooterVue />
</template>

<script>
import NavbarVue from '../components/Navbar.vue';
import About from '../components/About.vue';
import HdrBannerVue from '../components/HdrBanner.vue';
import EducationVue from '../components/Education.vue';
import WebProjectsVue from '../components/WebProjects.vue'
import FooterVue from '../components/Footer.vue';
  export default {
    name: 'home',
    components: { NavbarVue, HdrBannerVue, About, FooterVue, EducationVue, WebProjectsVue },
    mounted(){
      this.animateTxt(),
      this.showTxt()
    },
    methods: {
      animateTxt(){
        const txt = document.getElementById("animate_text");

        const splitTxt = txt.innerText.split("");
  
  
        txt.innerText = "";
        let i = 0;
        setInterval(function () {
          addLetters();
        }, 100);
        function addLetters() {
          if (i < splitTxt.length) {
            txt.innerHTML += splitTxt[i];
            i++;
          }
        }
      },
      showTxt(){
        const txt = document.querySelector('.HS-link')
        txt.classList.add('show')
      }
    }
  }
</script>

<style lang="scss" scoped>
#home{
  .home-title{
    position: absolute;
    height: 100%;
    top: 0;
    left: 5%;
    color: white;
    align-content: space-evenly;
    h1{ font-size: 60px }
    a{
      left: 10%;
      font-size: 35px;
      max-width: max-content;
      opacity: 0;
      transition: ease-in-out 3s 4s;
    }
    a.show{
      opacity: 1;
    }
    @media (max-width: 550px) {
      height: 100%;
      width: 100%;
      display: grid;
      align-content: space-evenly;
      top: 0;
      left: 0;
      margin: auto;
      h1, a{
        text-align: center;
      }
      h1{ font-size: 50px;}
      a{ 
        left: 0;
        font-size: 30px;
        width: 90%;
        place-self: center; 
      }
    }
  }
}
</style>