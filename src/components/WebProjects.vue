<template>
    <div class="container-fluid container-md portfolio-container">
        <div class="row portfolio">
          <div class="row title-portfolio">
            <h3>Portfolio</h3>
            <span>Je vous présente les projets que j'ai réalisé lors de ma formation de Développeur Web</span>
          </div>

          <div id="portfolio" class="container carousel-container">

            <button type="button" name="position" class="cbp_tmicon btn"></button>
            <button type="button" name="position" class="cbp_tmicon btn"></button>
            <button type="button" name="position" class="cbp_tmicon btn" checked></button>
            <button type="button" name="position" class="cbp_tmicon btn"></button>
            <button type="button" name="position" class="cbp_tmicon btn"></button>
            <button type="button" name="position" class="cbp_tmicon btn"></button>

            <main id="carousel" class="container">
              <div class="item">
                <img src="../assets/images/javascript.png" alt="">
                <div class="paraph"><p>Transformer une maquette en site Web avec HTML5 et CSS3</p></div>

              </div>
              <div class="item">
                <img src="../assets/images/javascript.png" alt="">
                <div class="paraph"><p>Construire une API sécurisée pour une application</p></div>
              </div>
              <div class="item">
                <img src="../assets/images/javascript.png" alt="">
                <div class="paraph"><p>Construire un réseau social d'Entreprise avec Vue.JS et MySQL</p></div>
              </div>
              <div class="item">
                <img src="../assets/images/javascript.png" alt="">
                <div class="paraph"><p>Construire un site web E-commerce</p></div>
              </div>
              <div class="item">
                <img src="../assets/images/javascript.png" alt="">
                <div class="paraph"><p>Référencement naturel d'un site web existant</p></div>
              </div>
              <div class="item">
                <img src="../assets/images/javascript.png" alt="">
                <div class="paraph"><p>Dynamiser une page web avec des animations CSS</p></div>
              </div>
            </main>
          </div>         
        </div>
    </div>
</template>

<script>
export default {
    name: 'WebProjects',
}
</script>

<style lang="scss" scoped>
.portfolio-container{
  .row.portfolio{
    .title-portfolio{
      justify-content: center;
      h3{
        padding: 50px;
        text-align: center;
        width: 50%;
        border-bottom: 2px solid;
      }
      span{
        text-align: center;
        font-size: 17px;
        padding: 40px;
      }
    }
  }
}
.carousel-container{
    display: grid;
    margin-bottom: 50px;
    .cbp_tmicon{
      z-index: 1;
      width: 40px;
	    height: 40px;
	    font-family: "ecoico";
	    speak: none;
	    font-style: normal;
	    font-weight: normal;
      font-variant: normal;
      text-transform: none;
      font-size: 1.4em;
      line-height: 40px;
      -webkit-font-smoothing: antialiased;
      position: absolute;
      color: #fff;
      background: #46a4da;
      border-radius: 50%;
      box-shadow: 0 0 0 8px #afdcf8;
      text-align: center;
      bottom: -15px;
      margin: 0 0 0 -25px;
      @media (min-width: 300px) and (max-width: 425px) {
        width: 15px;
        height: 25px;
        bottom: -7px;
        margin: 0 0 0 -17px;

      }
      @media (min-width: 666px) {
        width: 30px;
        height: 30px;
        bottom: -10px;
      }
    }
}
.carousel-container:before{
  content: "";        
  position: absolute; 
  bottom: 0;
  width: 100%;
  height: 10px;
  background: #afdcf8;
}
#carousel {
  grid-row: 1 / 2;
  grid-column: 1 / 8;
  height: 380px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  transform-style: preserve-3d;
  perspective: 600px;
  --items: 6;
  --middle: 4;
  --position: 3;
  @media (max-width: 667px) {
    overflow: overlay;
  }
  div.item {
    height: 280px;
    display: grid;
    align-content: space-evenly;
    border: 1px solid lightgrey;
    border-radius: 15px;
    text-align: center;
    position: absolute;
    width: 300px;
    opacity: 80%;
    background: linear-gradient(184deg, #24a4ea, #379deb 45%, #9D01AD);
    img{
      width: 50%;
      justify-self: center;
    }
    .paraph{
      color: white;
      padding: 5px;
      p{ height: 50px}
    }

  --r: calc(var(--position) - var(--offset));
  --abs: max(calc(var(--r) * -1), var(--r));
  transition: all 0.25s linear;
  transform: rotateY(calc(0deg * var(--r))) translateX(calc(-300px * var(--r)));
  z-index: calc((var(--position) - var(--abs)));
 
  
}
div.item:nth-of-type(1) {
  --offset: 1;
}
div.item:nth-of-type(2) {
  --offset: 2;
}
div.item:nth-of-type(3) {
  --offset: 3;
}
div.item:nth-of-type(4) {
  --offset: 4;
}
div.item:nth-of-type(5) {
  --offset: 5;
}
div.item:nth-of-type(6) {
  --offset: 6;
}
}



button:nth-of-type(1) {
  grid-column: 2 / 3;
    grid-row: 2 / 3;
}
button:nth-of-type(1):focus ~ main#carousel {
  --position : 1;
}
button:nth-of-type(2) {
  grid-column: 3 / 4;
  grid-row: 2 / 3;
}
button:nth-of-type(2):focus ~ main#carousel {
  --position : 2;
}
button:nth-of-type(3) {
  grid-column: 4 / 5;
  grid-row: 2 / 3;
}
button:nth-of-type(3):focus ~ main#carousel {
  --position : 3;
}
button:nth-of-type(4) {
  grid-column: 5 / 6;
  grid-row: 2 / 3;
}
button:nth-of-type(4):focus ~ main#carousel {
  --position : 4;
}
button:nth-of-type(5) {
  grid-column: 6 / 7;
  grid-row: 2 / 3;
}
button:nth-of-type(5):focus ~ main#carousel {
  --position : 5;
}
button:nth-of-type(6) {
  grid-column: 7 / 8;
  grid-row: 2 / 3;
}
button:nth-of-type(6):focus ~ main#carousel {
  --position : 6;
}

  

  
  // .row.portfolio-content{
  //   height: 300px;
  //   justify-content: center;
  //   .card{
  //     background: linear-gradient(184deg, #24a4ea, #379deb 45%, #9D01AD);
  //     opacity: 80%;
  //     justify-content: space-around;
  //     transition: transform .2s;
  //     &:hover{
  //       transform: scale(1.1);
  //       img{ display: none;}
  //       .paraph{display: block;}
  //     }
  //     img{
  //       width: 50%;
  //       align-self: center;
  //     }
  //     .paraph{
  //       color:white;
  //       display: none;
  //     }
  //   }


</style>