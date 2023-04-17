<template>

<div id="Banner">
    <div class="banner">
        <img src="../assets/banner.png" alt="">
    </div>

</div>

</template>

<script>
export default {
    name: 'Banner',
    mounted(){
      this.particles()
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
        });
      }
    }
}
</script>

<style lang="scss">
#Banner{
    max-width: 100%;
    height: 100%;
    .banner img {
        width: 100%;
        filter: blur(1px);
    }

}
</style>