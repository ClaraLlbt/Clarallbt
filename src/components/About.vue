<template>
    <div id="about" class="container-fluid">

        <div class="row presentation">
          <div class="col-11 col-md-12 col-lg-4 about-blc">
                <div class="bckgrd-color"></div>
                <div class="p">
                    <h2>Welcom !</h2>
                    <p class="about-me">Développeur Web Junior, basée à Boulogne-sur-mer et récemment diplomée, 
                      je suis à la recherche d'expériences professionnelles riches et motivantes. 
                      Artistique et manuelle, je suis passionnée par le dessin et la création. 
                      Geek, j'aime allier les nouvelles technologies à l'art. C'est pourquoi je cherche à évoluer dans le domaine du développement web 
                      afin de pouvoir mettre mes nouvelles compétences à profit dans un environnement en adéquation avec qui je suis.</p>
                      <div class="row softskills">
                        <h3>Mes qualités</h3>
                        <p>&#187 L'ecoute</p>
                        <p>&#187 Rigueur et organisation </p>
                        <p>&#187 Un sens artistique dans chaque projet</p>
                        <p>&#187 La sécurité et l'accessibilité</p>
                        <p>&#187 L'auto-évaluation</p>
                      </div>
                </div>

            </div>

            <div class="col-11 col-md-12 col-lg-6" id="skills">
                <div class="row development bloc-1">
                    <div class="col-md-3 code-icon icon-1">
                        <i id="icon1-color" class="bi bi-code"></i>
                    </div>
                    <div class="col-md-9 dev-skills" data-mdb-animation-on-scroll="repeat">
                        <h3 id="icon1-color">Développement</h3>
                        <div class="row">
                            <div class="col-6">
                                <h4>Backend</h4>
                                <p>SQL</p>
                                <p>SEO</p>
                                <p>API REST</p>
                                <p>ExpressJS</p>
                            </div>
                            <div class="col-6">
                                <h4>Frontend</h4>
                                <p>HTML/CSS/Bootstrap/Sass</p>
                                <p>NodeJS</p>
                            <p>Javascript</p>
                            <p>angularJS/Vuejs</p>
                            </div>
                        </div>
                    </div>
                </div> 
                <div class="row development bloc-2">
                    <div class="col-md-9 dev-skills">
                        <h3 id="icon2-color">Design</h3>
                        <p>Clip Studio Paint</p>
                        <p>Adobe Illustrator/Indesign/Photoshop</p>
                     </div>
                    <div class="col-md-3 code-icon" id="icon2-color">
                        <i class="bi bi-palette2"></i>
                    </div>
                </div>
                <div class="row development bloc-3">
                    <div class="col-md-3 code-icon" id="icon3-color">
                        <i class="bi bi-pc-display"></i>
                     </div>
                    <div class="col-md-9 dev-skills">
                        <h3 id="icon3-color">Environnement de travail</h3>
                        <p>IDE : Visual Studio Code</p>
                        <p>Workflow : Github</p>
                        <p>Bureautique : Google Drive/Microsoft Office/Libre Office</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    name: "about",
    mounted(){ this.slideBloc() },

    
    methods: {
        slideBloc(){
            const el = document.querySelector('#skills')
            const blocSlide1 = document.querySelector('.bloc-1');
            const blocSlide2 = document.querySelector('.bloc-2');
            const blocSlide3 = document.querySelector('.bloc-3');

            window.addEventListener('scroll', () => { 
                const { scrollTop, scrollHeight ,clientHeight} = document.documentElement;
                const topElementToTopViewport = el.getBoundingClientRect().top
                if(scrollTop > (scrollTop + topElementToTopViewport).toFixed() - clientHeight * 0.30){
                    blocSlide1.classList.add('active');
                    blocSlide2.classList.add('active2');
                    blocSlide3.classList.add('active3')
                }
            });
        }
    }
}
</script>

<style lang="scss">

#about{
  padding: 100px 0;
  @media (min-width: 300px) and (max-width: 1025px) {
    padding-top: 95px;
    padding-bottom: 0;
  }
  .presentation{
    margin: auto;
    align-items: center;
    justify-content: center;
    @media (min-width: 300px) and (max-width: 1000px) {
    
  }
  .about-blc{
      border: 1px dotted #C3F672;
      border-radius: 15px;
      margin: auto;
      background: white;
      @media (max-width: 1024px){
          margin-bottom: 50px;
        }
      .bckgrd-color{
        height: 100%;
        position: absolute;
        width: 100%;
        background: #778DFB;            
        border-radius: 15px;
        z-index: -1;
        top: 10px;          
        left: 10px;
        @media (max-width: 1024px){
          top: -6px;              
          left: 0;
        }
      }
      h2{
        font-family: Amsterdam Four_ttf;
        text-align: center;
        font-weight: 600;
        font-size: xxx-large;
        max-width: fit-content;
        background: white;
        padding: 10px;
        margin: auto;
        position: relative;
        top: -40px;
      }
      .about-me{
        text-align: justify;
        padding: 0px 10px;
        margin: 0;
      }
      .row.softskills{
        padding: 10px;
        h3{ 
          font-family: 'Amsterdam';
          font-weight: bold;
          font-size: large;
          padding: 15px;
        }
        p{
          padding: 0px 15px;
          margin: 0;
        }
      }
    }
    #skills{
      overflow: hidden;
      margin: auto;
      h3{ font-size: 25px;}
      h4{font-size: large;}
      .development{  
        #icon1-color {color: #396CF1;}
          #icon2-color {
            color: #f89b3b;
            i{
              font-size: 70px;
            }
          }
          #icon3-color {
            color: #F853B8;
            i{
              font-size: 70px;
            }
          }
        .code-icon {
          align-self: center;
          text-align: center;
          font-size: 100px;
        }
        .dev-skills {
          padding: 15px;
          background: #F8F8F8;
          border-radius: 10px;
          align-self: center;
          
        }
        p {
          margin-bottom: 0;
          font-weight: 600;
          @media (max-width: 776px){
            overflow-wrap: break-word;
            font-size: 12px;
          }
        }
        
      }
      //animation blocs development
      .bloc-1{
        transform: translateX(-100%);
        opacity: 0;
        transition: transform 2s ease-in-out,
        opacity 0.6s ease-in-out;
      } .bloc-1.active{
        transform: translateX(0%);
        opacity: 1;
      }
      .bloc-2{
        transform: translateX(120%);
        opacity: 0;
        transition: transform 2s ease-in-out,
        opacity 0.6s ease-in-out;
        @media (max-width: 776px){
          flex-direction: column-reverse;
        }
      } .bloc-2.active2{
        transform: translateX(0%);
        opacity: 1;
      }
      .bloc-3{
        transform: translateX(-100%);
        opacity: 0;
        transition: transform 2s ease-in-out,
        opacity 0.6s ease-in-out;
      } .bloc-3.active3{
        transform: translateX(0%);
        opacity: 1;
      }

      @media (max-width: 425px){
        padding-bottom: 50px;
      }
    }
  }
}
</style>