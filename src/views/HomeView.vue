<template>
  <!--HEADER-->
  <div id="home" class="home">
    <!--Navbar + Header Banner-->
    <NavbarVue />

    <Banner />

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
import EducationVue from '../components/Education.vue';
import WebProjectsVue from '../components/WebProjects.vue'
import FooterVue from '../components/Footer.vue';
import Banner from '../components/Banner.vue'
  export default {
    name: 'home',
    components: { NavbarVue, Banner ,About, FooterVue, EducationVue, WebProjectsVue },
    mounted(){
    },
    methods: {
    }
  }
</script>

<style lang="scss" scoped>
</style>