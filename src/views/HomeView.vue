<template>
  <!--HEADER-->
    <!--Navbar + Header Banner-->
    <NavbarVue />

    <Banner />


  <!--About Container-->
  <About/>
  <!--Education Container-->
  <EducationVue />
  <!--Web Projects Container-->
  <Portfolio />
  
  <!--Footer-->
  <Contact />

</template>

<script>
import NavbarVue from '../components/Navbar.vue';
import About from '../components/About.vue';
import EducationVue from '../components/Education.vue';
import FooterVue from '../components/Footer.vue';
import Banner from '../components/Banner.vue';
import Portfolio from '../components/Portfolio.vue';
import Contact from '../components/Contact.vue';
  export default {
    name: 'home',
    components: { NavbarVue, Banner ,About ,FooterVue, EducationVue, Portfolio, Contact},
  }
</script>

<style lang="scss">
</style>