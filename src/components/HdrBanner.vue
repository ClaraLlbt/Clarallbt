<template>
    <div class="hero" id="tsparticles">      
      <div class="w wave"></div>
      <div class="w wave2"></div>
      <div class="w wave3"></div>
      <div class="w wave4"></div>
    </div>
</template>

<script>
export default {
    name: 'HdrBanner',
    mounted(){
      this.particles()
    },
    methods: {
      particles(){
       
        const hdr = document.querySelector('.header')
        const hero = document.querySelector('.hero')

        window.addEventListener('scroll', () => { 
          const { scrollTop, scrollHeight ,clientHeight} = document.documentElement;
          const topElementToTopViewport = hero.getBoundingClientRect().top
          if(scrollTop > (scrollTop + topElementToTopViewport).toFixed() - clientHeight >= -120){
            hdr.classList.add('bg');
          }
        });


            particlesJS("tsparticles", {
                "particles": {
    "number": {
      "value": 16,
      "density": {
        "enable": true,
        "value_area": 600
      }
    },
    "color": {
      "value": "#ffffff"
    },
    "shape": {
      "type": "circle",
      "stroke": {
        "width": 0,
        "color": "#000000"
      },
      "polygon": {
        "nb_sides": 5
      },
      "image": {
        "src": "img/github.svg",
        "width": 100,
        "height": 100
      }
    },
    "opacity": {
      "value": 0.25,
      "random": false,
      "anim": {
        "enable": false,
        "speed": 1,
        "opacity_min": 0.1,
        "sync": false
      }
    },
    "size": {
      "value": 10,
      "random": true,
      "anim": {
        "enable": false,
        "speed": 2,
        "size_min": 0.1,
        "sync": false
      }
    },
    "line_linked": {
      "enable": false,
      "distance": 300,
      "color": "#ffffff",
      "opacity": 0,
      "width": 0
    },
    "move": {
      "enable": true,
      "speed": 2,
      "direction": "top",
      "random": true,
      "straight": true,
      "out_mode": "out",
      "bounce": false,
      "attract": {
        "enable": false,
        "rotateX": 600,
        "rotateY": 1200
      }
    }
  },
  "interactivity": {
    "detect_on": "canvas",
    "events": {
      "onhover": {
        "enable": false,
        "mode": "repulse"
      },
      "onclick": {
        "enable": false,
        "mode": "push"
      },
      "resize": true
    },
    "modes": {
      "grab": {
        "distance": 800,
        "line_linked": {
          "opacity": 1
        }
      },
      "bubble": {
        "distance": 800,
        "size": 80,
        "duration": 2,
        "opacity": 0.8,
        "speed": 3
      },
      "repulse": {
        "distance": 400,
        "duration": 0.4
      },
      "push": {
        "particles_nb": 4
      },
      "remove": {
        "particles_nb": 2
      }
    }
  },
  "retina_detect": true
      })}
    }
    
    
}
</script>

<style lang="scss">
body {
   min-height: 200vh;
   margin: 0;
   font-family: "Quicksand", sans-serif;
   overflow-x: hidden;
   a {
      color: inherit;
      text-decoration: none;
   }
   
   .hero {
      overflow: hidden;
      position: relative;
      height: calc(100vh + 80px);
      min-height: 200px;
      background: #ffce54;
      background: linear-gradient(100deg, #24a4ea, #379deb 25%, #b76bf0);
      .w {
         position: absolute;
         top: 100%;
         left: -25vw;
         right: 0px;
         background: url(https://i.koya.io/whitewave2.svg);
         background-position: center;
      }
      .wave {
         height: 200px;
         transform: translateY(-40px);
      }
      .wave2 {
         height: 240px;
         transform: translateY(-80px);
         background-size: 960px 240px;
         opacity: 0.5;
         left: -80vw;
         right: -5vw;
      }
      .wave3 {
         height: 220px;
         transform: translateY(-120px);
         background-size: 880px 220px;
         opacity: 0.33;
         left: 0vw;
         right: -20vw;
      }
      .wave4 {
         height: 280px;
         transform: translateY(-160px);
         background-size: 1120px 280px;
         opacity: 0.1;
         left: 0vw;
         right: -40vw;
      }
   }
}


</style>