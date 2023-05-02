<template>
  <nav id="nav" class="navbar navbar-expand-lg">
        <a class="navbar-brand" href="#home"><img src="../assets/Logo-Kala-Dev.svg" alt=""></a>
        
        <div class="" id="navbarNav">
            <ul class="navbar-nav">
                <li class="nav-item active">
                    <a class="nav-link link-about" href="#about">A propos
                        <div class="border-effect"></div>
                    </a>
                    <a class="nav-link icon-about" href="#"><i class="bi bi-house-door-fill"></i>
                        <div class="border-effect"></div>
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link link-education" href="#education">Parcours
                        <div class="border-effect"></div>
                    </a>
                    <a class="nav-link icon-education" href="#education"><i class="bi bi-gear-wide-connected"></i>
                        <div class="border-effect"></div>
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link link-portfolio" href="#portfolio">Portfolio
                        <div class="border-effect"></div>
                    </a>
                    <a class="nav-link icon-portfolio" href="#portfolio"><i class="bi bi-envelope-at"></i>
                        <div class="border-effect"></div>
                    </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link link-contact" href="#contact">Contact
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
      this.responsiveIcons();
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
      responsiveIcons(){
            const iconAbout = document.querySelector('.icon-about')
            const iconEducation = document.querySelector('.icon-education')
            const iconPortfolio = document.querySelector('.icon-portfolio')
            const iconContact = document.querySelector('.icon-contact')

            if (window.matchMedia("(max-width: 768px)").matches) {
                /* La largeur minimum de l'affichage est 600 px inclus */
                console.log("format mobile detecté")
                iconAbout.classList.add('mbl')
                iconEducation.classList.add('mbl')
                iconPortfolio.classList.add('mbl')

            } else {
                console.log("format mobile non detecté")
                /* L'affichage est inférieur à 600px de large */
            }
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
  height: 65px;
  .navbar-brand{ 
    color: #C1FF72;
    position: absolute;
    width: 25%;
    z-index: 2;
    img{
      width: 65%;
      margin: 0 15px;
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
      .icon-about, .icon-education, .icon-portfolio, .icon-contact{
        display: none;
      }
    }
  }
}
.bg{
  backdrop-filter: contrast(0.5);
}

// Mobile Version
@media (max-width: 768px) {
    nav{
        padding: 5px 0px;
        #navbarNav{
            ul{
                display: flex;
                flex-direction: row;
                justify-content: center;
                align-items: center;
                li{
                    margin: 0 10px;
                    font-size: 20px;
                    
                    .icon-about.mbl, .icon-education.mbl, .icon-portfolio.mbl,  .icon-contact.mbl{
                        display: block;
                    }
                    .link-about , .link-portfolio , .link-education ,  .link-contact{
                        display: none;
                    }

                }
                
            }
        }
    }
}
</style>