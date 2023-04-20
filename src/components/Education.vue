<template>
  <div id="education" class="container-fluid">
    <div class="row education">
      <div class="col-md-6 img-education">          
        <div class="img"></div>
      </div>
      <div class="col-md-6 timeline-design">
        <div class="row dl-cv">
          <h3 class="col-12 col-md-4 title">Mes diplômes</h3> 
          <div class="col-12 col-md-6 btn-dl-cv">
            <a href="/ClaraLaliberT/lib/web/CV_LALIBERTE_CLARA.pdf" download>                  
              <button type="button" class="btn btn-light"><i class="bi bi-file-pdf"></i> Télécharger mon CV</button>
            </a>
          </div>
        </div>
          <ul class="cbp_tmtimeline">
		        <li>
			        <time class="cbp_tmtime">
		            <span>BAC+2</span>
		        		<span>2022</span>
			        </time>
			        <div class="cbp_tmicon icon-1"></div>
			        <div class="cbp_tmlabel label-1">
				        <h3>Dévloppeur Web</h3>
				        <p>Création Backend/Frontend; création et gestion de bases de données</p>
			        </div>  
		        </li>
            <li >
			        <time class="cbp_tmtime">
		            <span>DEUST</span>
		        		<span>2019</span>
			        </time>
			        <div class="cbp_tmicon icon-2"></div>
			        <div class="cbp_tmlabel label-2">
				        <h3>Formation BCMM</h3>
				        <p>Formation en Bureautique, Communication et Multimédias - en alternance chez Casteleyn/Régiopack</p>
			        </div>  
		        </li>
            <li >
			      <time class="cbp_tmtime">
		          <span>BAC</span>
		        	<span>2016</span>
			      </time>
			      <div class="cbp_tmicon icon-3"></div>
			      <div class="cbp_tmlabel label-3">
				      <h3>DAEU (scientifiques)</h3>
				      <p>Diplôme d'accès aux études universitaire - Equivalence Bac</p>
			      </div>  
		      </li>
	      </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'certificates',
    mounted(){ this.EducationSlide() },
    methods:{
        EducationSlide(){
        const educationRow = document.querySelector('#education');
        const educ1 = document.querySelector('.cbp_tmlabel.label-1');
        const icon1 = document.querySelector('.cbp_tmicon.icon-1');

        const educ2 = document.querySelector('.cbp_tmlabel.label-2');
        const icon2 = document.querySelector('.cbp_tmicon.icon-2');

        const educ3 = document.querySelector('.cbp_tmlabel.label-3');
        const icon3 = document.querySelector('.cbp_tmicon.icon-3')
        
        window.addEventListener('scroll', () => { 
            const { scrollTop, scrollHeight ,clientHeight} = document.documentElement;
            const topElementToTopViewport = educationRow.getBoundingClientRect().top
            if(scrollTop > (scrollTop + topElementToTopViewport).toFixed() - clientHeight * 0.30){
            educ1.classList.add('active1');
            icon1.classList.add('active');

            educ2.classList.add('active2');
            icon2.classList.add('active3');

            educ3.classList.add('active5');
            icon3.classList.add('active4');
            }
        });
        }
    }
}
</script>

<style lang="scss" scoped>
#education{
    .education{
        height: 100%;
        contain: content;
        padding-top: 60px;
        overflow: hidden;
        .img-education{
            height: 100%;
            padding: 0;
            .img{
                height: 555px;
                background-image: url(../assets/images/educationcomputer.jpg);
                background-position: center;
            }
        }
        .timeline-design{
          display: grid;
          .dl-cv{
            margin: 20px;
            .title{ color: #215B7D; }
            .btn-dl-cv{
              text-align: end;
            }
            @media (max-width: 767px) {
              .title , .btn-dl-cv{
                text-align: center;
              }
            }
          }
            .cbp_tmtimeline {
	            margin: 30px 0 0 0;
	            padding: 0;
	            list-style: none;
              position: relative;

              /*Translate Y */
              .cbp_tmicon, .cbp_tmlabel{
                transform: translateY(465px);
                opacity: 0;
                opacity: 1;
                transition: transform 2s ease-in-out, opacity 0.6s ease-in-out;
              }
              .cbp_tmicon.icon-1.active, .cbp_tmlabel.label-1.active1{
                transform : translateY(0px);
                opacity: 1;
              }
              .cbp_tmicon.icon-2.active3, .cbp_tmlabel.label-2.active2{
                transform : translateY(0px);
                opacity: 1;
              }
              .cbp_tmicon.icon-3.active4, .cbp_tmlabel.label-3.active5{
                transform : translateY(0px);
                opacity: 1;
              }
            }
            /* The line */
            .cbp_tmtimeline:before {
	            content: "";
              position: absolute;
              top: 0;
              bottom: 0;
              width: 10px;
              background: #afdcf8;
              left: 20%;
              margin-left: -10px;
            }
            .cbp_tmtimeline > li { position: relative; }
            /* The date/time */
            .cbp_tmtimeline > li .cbp_tmtime {
	            display: block;
              width: 15%;
              padding-right: 100px;
              position: absolute;
            }
            .cbp_tmtimeline > li .cbp_tmtime span {
	            display: block;
	            text-align: right;
            }
            .cbp_tmtimeline > li .cbp_tmtime span:first-child {
              font-size: 0.9em;
              color: #215B7D;
            }
            .cbp_tmtimeline > li .cbp_tmtime span:last-child {
	            font-size: 2.9em;
	            color: #215B7D;
            }

            /* Right content */
            .cbp_tmtimeline > li .cbp_tmlabel {
              margin: 0 0 15px 25%;
              background: #215B7D;
              color: #fff;
              padding: 10px;
              font-size: 1.2em;
              font-weight: 300;
              line-height: 1.4;
              position: relative;
              border-radius: 5px;
            }
            .cbp_tmtimeline > li .cbp_tmlabel h2 {
              margin-top: 0px;
              padding: 0 0 10px 0;
              border-bottom: 1px solid rgba(255, 255, 255, 0.4);
            }
            /* The triangle */
            .cbp_tmtimeline > li .cbp_tmlabel:after {
              right: 100%;
              border: solid transparent;
              content: " ";
              height: 0;
              width: 0;
              position: absolute;
              pointer-events: none;
              border-right-color: #215B7D;
              border-width: 10px;
              top: 10px;
            }
            /* The icons */
            .cbp_tmtimeline > li .cbp_tmicon {
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
              left: 20%;
              top: 0;
              margin: 0 0 0 -25px;
              
            }
            /* Example Media Queries */
          @media screen and (max-width: 65.375em) {
	          .cbp_tmtimeline > li .cbp_tmtime span:last-child {
		          font-size: 1.5em;
	          }
          }
          @media screen and (max-width: 47.2em) {
	          .cbp_tmtimeline:before {
		          display: none;
	          }
            .cbp_tmtimeline > li .cbp_tmtime {
		          width: 100%;
		          position: relative;
		          padding: 0 0 20px 0;
	          }
            .cbp_tmtimeline > li .cbp_tmtime span {
		          text-align: left;
	          }
            .cbp_tmtimeline > li .cbp_tmlabel {
		          margin: 0 0 30px 0;
		          padding: 1em;
		          font-weight: 400;
		          font-size: 95%;
	          }
            .cbp_tmtimeline > li .cbp_tmlabel:after {
		          right: auto;
		          left: 20px;
		          border-right-color: transparent;
		          border-bottom-color: #215B7D;
		          top: -20px;
	          }
          	.cbp_tmtimeline > li:nth-child(odd) .cbp_tmlabel:after {
		          border-right-color: transparent;
		          border-bottom-color: #215B7D;
          	}
            .cbp_tmtimeline > li .cbp_tmicon {
		          position: relative;
		          float: right;
		          left: auto;
		          margin: -55px 5px 0 0px;
	          }
          }
        }
      }    
  }
</style>