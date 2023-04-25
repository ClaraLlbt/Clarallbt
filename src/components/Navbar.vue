<template>
  <nav id="nav" class="navbar navbar-expand-lg">
        <a class="navbar-brand" href="#home"><img src="../assets/Logo-Kala-Dev.svg" alt=""></a>
        
        <div class="" id="navbarNav">
            <ul class="navbar-nav">
                <li class="nav-item active">
                    <a class="nav-link link-home" href="#about">A propos
                        <div class="border-effect"></div>
                    </a>
                    <!-- <a class="nav-link icon-home" href="#"><i class="bi bi-house-door-fill"></i>
                        <div class="border-effect"></div>
                    </a> -->
                </li>
                <li class="nav-item">
                    <a class="nav-link link-services" href="#education">Parcours
                        <div class="border-effect"></div>
                    </a>
                    <!-- <a class="nav-link icon-services" href="#education"><i class="bi bi-gear-wide-connected"></i>
                        <div class="border-effect"></div>
                    </a> -->
                </li>
                <li class="nav-item">
                    <a class="nav-link link-contact" href="#portfolio">Portfolio
                        <div class="border-effect"></div>
                    </a>
                    <!-- <a class="nav-link icon-contact" href="#portfolio"><i class="bi bi-envelope-at"></i>
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
      this.navbar()
    },
    methods: {
      //Darkmod function 
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
      navbar(){
        const doc = document.documentElement
        console.log(doc);
        const navbar = document.querySelector('#nav')

        window.addEventListener('scroll', () => { 
            const { scrollTop, scrollHeight ,clientHeight} = document.documentElement;
            const topElementToTopViewport = doc.getBoundingClientRect().top
            if(scrollTop > (scrollTop + topElementToTopViewport).toFixed() - clientHeight * 0.30){
              navbar.classList.add('bg')
            }
        });
      }
      
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
  height: 50px;
  .navbar-brand{ 
    color: #C1FF72;
    position: absolute;
    width: 25%;
    z-index: 2;
    img{
      width: 50%;
    }
  }
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

.bg{
  backdrop-filter: contrast(0.5);
}
</style>