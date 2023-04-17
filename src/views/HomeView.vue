<template>
  <!--HEADER-->
  <div id="home" class="home">
    <!--Navbar + Header Banner-->
    <NavbarVue />

    <Banner />

    <div class="row home-title">
      <img class="profil-pic" src="../assets/images/photo.svg" alt="">
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
import Banner from '../components/Banner.vue'
  export default {
    name: 'home',
    components: { NavbarVue, HdrBannerVue, About, FooterVue, EducationVue, WebProjectsVue, Banner },
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
    display: flex;
    justify-content: center;
    position: absolute;
    height: 100%;
    width: 100%;
    top: 0;
    color: white;
    align-content: space-evenly;
    .profil-pic{ 
      width: 100%;
      height: 32%;
    }
    h1{ 
      font-size: 60px;
      text-align: center;
     }
     h2{ text-align: center;}
    a{
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