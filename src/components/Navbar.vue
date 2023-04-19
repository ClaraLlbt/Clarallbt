<template>
  <nav class="navbar navbar-expand-lg">
        <a class="navbar-brand" href="#">Clara Laliberté</a>
        
        <div class="" id="navbarNav">
            <ul class="navbar-nav">
                <li class="nav-item active">
                    <a class="nav-link link-home" href="#">A propos
                        <div class="border-effect"></div>
                    </a>
                    <!-- <a class="nav-link icon-home" href="#"><i class="bi bi-house-door-fill"></i>
                        <div class="border-effect"></div>
                    </a> -->
                </li>
                <li class="nav-item">
                    <a class="nav-link link-services" href="#services">Parcours
                        <div class="border-effect"></div>
                    </a>
                    <!-- <a class="nav-link icon-services" href="#services"><i class="bi bi-gear-wide-connected"></i>
                        <div class="border-effect"></div>
                    </a> -->
                </li>
                <li class="nav-item">
                    <a class="nav-link link-contact" href="#contact">Portfolio
                        <div class="border-effect"></div>
                    </a>
                    <!-- <a class="nav-link icon-contact" href="#contact"><i class="bi bi-envelope-at"></i>
                        <div class="border-effect"></div>
                    </a> -->
                </li>
                <li class="nav-item">
                    <a class="nav-link icon-contact" href="#contact">Contact
                        <div class="border-effect"></div>
                    </a>
                </li>
                <button class="btn item-dark-reader">
                    <i class="bi bi-moon icon-moon" v-if="this.dark == false"></i>
                    <i class="bi bi-brightness-high icon-light" v-else-if="this.dark == true"></i>
                </button>
               
            </ul>
        </div>
        
  </nav>
</template>

<script>
import { useDark, useToggle } from "@vueuse/core";
  export default {
    name: "Navbar",
    data(){
      return {
        dark: '',
      }
    },
    mounted(){
      this.darkMod();
    },
    methods: {
      darkMod(){
        const isDark = useDark();
        const toggleDark = useToggle(isDark)
        this.dark = isDark

        console.log(this.dark);

        const btnDkMod = document.querySelector('.item-dark-reader')
        btnDkMod.addEventListener('click', function(){   
         toggleDark()
        })
      },
      
    }
    
  }
</script>

<style lang="scss" scoped>
nav{
  position: fixed;
  padding: 0;
  top: auto;
  z-index: 2;
  width: 100%;
  overflow: hidden;
  backdrop-filter: contrast(0.5);
  height: 50px;
  .navbar-brand{ color: #C1FF72; }
  #navbarNav{
    width: 100%;
    ul{
      justify-content: center;
      align-items: center;
      li{
        a{ color: #C1FF72; }
        a i { font-size: 20px;}
        &:hover{
          .border-effect{
            margin: auto;
            border-bottom: 1px solid #C1FF72;
            animation: borderEffectOnHover 1s ease-in-out;
          }
          @keyframes borderEffectOnHover {
            from{
              width: 0%;
            }
            to{
              width: 100%;
            }
          }
        }
      }
      .item-dark-reader{
        color: #C1FF72;
        position: absolute;
        right: 20px;
        font-size: 20px;
      }            
      // .icon-home, .icon-services, .icon-contact{
      //   display: none;
      // }
    }
  }
}
</style>