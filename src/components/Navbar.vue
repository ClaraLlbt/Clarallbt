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
        name: 'navbar'    
  }
</script>

<style lang="scss" scoped>
.header {
      z-index: 1000;
      position: fixed;
      top: 0px;
      left: 0px;
      right: 0px;
      padding: 0px 20px;
      background: linear-gradient(
         100deg,
         rgba(36, 164, 234, 0),
         rgba(55, 157, 235, 0) 25%,
         rgba(183, 107, 240, 0)
      );
      transition: background 0.25s ease;

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
         color: white;
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
         background: #2C0437;
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