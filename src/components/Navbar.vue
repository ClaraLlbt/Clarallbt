<template>
  <nav id="navbar" class="header container-fluid navbar navbar-expand-lg">
    <router-link to="/" class="name navbar-brand">Clara Laliberté</router-link>

    <button name="navbar button" aria-label="navbar button"  class="navbar-toggler bg-light" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasNavbar" aria-controls="offcanvasNavbar">
      <span class="navbar-toggler-icon"></span>
    </button>
    
  <div class="offcanvas offcanvas-end col col-md-" tabindex="-1" id="offcanvasNavbar" aria-labelledby="offcanvasNavbarLabel">
    <div class="offcanvas-header">
      <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close" name="close button"></button>
    </div>
    
    <div class="offcanvas-body">
    <div class="menu">
      <ul class="navbar-nav mr-auto mb-2 mb-lg-0">
        <li class="nav-item tohide"><a href="#about" class="link about">A propos</a></li>
        <li class="nav-item tohide"><a href="#education" class="link education">Parcours</a></li>
        <li class="nav-item tohide"><a href="#portfolio" class="link portfolio">Portfolio</a></li>
        <li class="nav-item tohide"><router-link to="/contact/">Contact</router-link></li>
      </ul>
    </div>
  </div>
  </div>
    <!--Design Menu Contact Page-->
    <div class="menu-contact">
      <ul class="navbar-nav mr-auto mb-2 mb-lg-0">
        <li class="nav-item toshow"><a class="home" href="/"><router-link to="/"><i class="bi bi-house-door-fill light"></i></router-link></a></li>
      </ul>
    </div>
  </nav>
</template>

<script>

  export default {
      name: 'navbar',
      mounted(){
        this.particles
      },   
      methods: {
        particles(){
            const hdr = document.querySelector('.header')
            console.log(hdr);
            const hero = document.querySelector('#about')
            console.log(hero);
    
            window.addEventListener('scroll', () => { 
              const { scrollTop, scrollHeight ,clientHeight} = document.documentElement;
              const topElementToTopViewport = hero.getBoundingClientRect().top
              console.log(topElementToTopViewport);
              if(scrollTop > (scrollTop + topElementToTopViewport).toFixed() - clientHeight >= -120){
                hdr.classList.add('bg');
              }
            })
        }
      }, 
}
</script>

<style lang="scss" scoped>
.header {
  position: fixed;
  padding: 0;
  top: auto;
  z-index: 2;
  width: 100%;
  overflow: hidden;
  height: 50px;

    .menu{
    width: 100%;
    justify-content: right;
    ul{
      width: 50%;
      display: flex;
      justify-content: space-around;
      float: right;
    }
    @media (max-width: 991px){
      height: 100%;
      ul{
        width: 100%;
        align-items: center;
        justify-content: space-around;
        height: 100%;
        li{
          a{color: #485665;}
        }
      }
    }
    
  }
    .offcanvas-end.hidden{
      transform: translateX(100%);
      transition: transform .3s ease-in-out;
      visibility: hidden;
    }
    .name,
    .nav-item a {
       display: inline-block;
       color: #C1FF72;
       font-size: 24px;
       line-height: 42px;
       font-smoothing: antialiased;
    }
    .name {
       font-weight: bold;
    }
    .nav-item a {
       float: right;
    }
    &.bg {
       backdrop-filter: blur(100px);
    }

    .menu-contact{
      display: none;
      justify-content: right;
      ul{
        display: flex;
        justify-content: space-around;
        float: right;
        .nav-item a i{
          font-size: 40px;
        }
      }
    }
 }
</style>