<template>
    <div id="contact" class="container-fluid contact-ctr">
        <div class="row">
            <div class="col contact">
				<div class="span-txt">
                <h2>Contactez-moi !</h2>
                <span class="span-1">Vous souhaitez discuter de mes motivations ? Je vous invite à me contacter. Vous pouvez télécharger mon cv ou utiliser le formulaire.</span>
                <div class="col-12 btn-dl-cv">
                    <a href="/ClaraLaliberT/lib/web/CV_LALIBERTE_CLARA.pdf" download="">
                        <button type="button" class="btn"><i class="bi bi-file-pdf"></i> Télécharger mon CV</button>
                    </a>
                </div>
                <span class="span-2">A Bientôt !</span>
           		</div>
				   <div class="envlp">
					<div class="col-lg-12 letter-image">
					<div class="animated-mail">
						<div class="back-fold"></div>
						<div class="letter">
							<div class="letter-border"></div>
							<div class="letter-title"></div>
							<div class="letter-context"></div>
							<div class="letter-stamp">
								<div class="letter-stamp-inner"></div>
							</div>
		
						</div>
		
						<div class="top-fold"></div>
		
						<div class="body"></div>
		
						<div class="left-fold"></div>
	
					</div>
					<div class="shadow"></div>
				</div>
				</div>
			</div>
			<div class="col form">
				<form id="form" method="POST">
                    <h3>Formulaire de contact</h3>
                    <div>
                        <label for="reply_to" class="form-label">Email:</label>
                        <input  v-model="email" type="email" class="form-control" id="reply_to" name="reply_to" placeholder="Laissez moi votre Email" aria-describedby="emailHelp" required>
                    </div>
                    <div>
                        <label for="message" class="form-label">Votre message:</label>
                        <textarea v-model="message" class="form-control" id="message" name="message" rows="3" placeholder="Je serais ravie de prendre contact avec vous..." required></textarea>
                    </div>
                    <div class="button" >
                        <button id="sendBtn" @click="sendEmail()" type="submit" value="Send Email" class="btn">Envoyer</button>
                    </div>
                </form>
			</div>
        
		</div>
    </div>
	<Footer />
</template>

<script>
import emailjs from "emailjs-com"
import Footer from "./Footer.vue"
export default {
        name: 'Contact',
		components: {Footer},
        data(){
            return{
                email: '',
                message: '',
            }
        },
        mounted(){
			this.displayEnv()
        },
        methods: {
			displayEnv() {
				const contactCtr = document.querySelector('.contact-ctr')
        		const letterImg = document.querySelector('.letter-image')

        window.addEventListener('scroll', () => { 
            const { scrollTop, scrollHeight ,clientHeight} = document.documentElement;
            const topElementToTopViewport = contactCtr.getBoundingClientRect().top
            if(scrollTop > (scrollTop + topElementToTopViewport).toFixed() - clientHeight * 0.30){
				letterImg.classList.add('display')
            }
        });
			},
            sendEmail() {
                const btn = document.querySelector('#sendBtn');
                const messArea = document.querySelector('#message');
                const emailArea = document.querySelector('#reply_to');
                const form = document.getElementById('form').addEventListener('submit', function(event) {
                    event.preventDefault();
                    
                    btn.innerText = "En cours..."
                    const serviceID = 'service_696tmpa';
                    const templateID = 'template_bhiwqld';
                    const userId = 'OkYb3_3x2XbgyN8aT';
   
                    emailjs.sendForm(serviceID, templateID, this ,userId, {
                        email: this.email,
                        message: this.message
                    }) .then((res) => {
                        btn.innerText = 'Email Envoyé';
                        document.location.href = "/ClaraLaliberT/";
                    
                    }) 
                    .catch ((err) => {
                        btn.innerText = 'Une erreur est survenue';
                    })
                });  
            }
        }
}

</script>

<style lang="scss">
.contact-ctr{
    height: 100vh;
	background: #380541;
	@media (max-width: 768px) {
		height: 100%;
            }
    .row{
        height: 100%;
        .contact{
			align-self: center;
    		text-align: center;
			margin-bottom: 30px;
			.span-txt{
				color: #C3F672;
				h2{ 
					font-family: 'Amsterdam Four_ttf';
					font-size: 40px;
					margin-bottom: 40px;
					@media (max-width: 768px) {
						margin: 40px auto;
            		}
				}
				.btn-dl-cv{
					margin: 15px 0;
              		a .btn{
                	padding: 15px;
                	color: #C3F672;
                	border: 1px #C3F672 solid;
                	box-shadow: 2px 1px 4px #C3F672;
              }
              a .btn:hover{
                box-shadow: 2px 1px 20px #C3F672;
               
              }
            }
			}
			.envlp{
				.letter-image {
	position: absolute;
	top: 100px;
	left: 50%;
	width: 200px;
	height: 200px;
	-webkit-transform: translate(-50%, -50%);
	-moz-transform: translate(-50%, -50%);
	transform: translate(-50%, -50%);
	cursor: pointer;
	@media (max-width: 768px) {
        position: relative;
            }
}

.animated-mail {
	position: absolute;
	height: 150px;
	width: 200px;
	-webkit-transition: .4s;
	-moz-transition: .4s;
	transition: .4s;
	
	.body {
		position: absolute;
		bottom: 0;
		width: 0;
		height: 0;
		border-style: solid;
		border-width: 0 0 100px 200px;
		border-color: transparent transparent #e95f55 transparent;
		z-index: 2;
	}
	
	.top-fold {
		position: absolute;
		top: 50px;
		width: 0;
		height: 0;
		border-style: solid;
		border-width: 50px 100px 0 100px;
		-webkit-transform-origin: 50% 0%;
		-webkit-transition: transform .4s .4s, z-index .2s .4s;
		-moz-transform-origin: 50% 0%;
		-moz-transition: transform .4s .4s, z-index .2s .4s;
		transform-origin: 50% 0%;
		transition: transform .4s .4s, z-index .2s .4s;
		border-color: #cf4a43 transparent transparent transparent;
		z-index: 2;
	}
	
	.back-fold {
		position: absolute;
		bottom: 0;
		width: 200px;
		height: 100px;
		background: #cf4a43;
		z-index: 0;
	}
	
	.left-fold {
		position: absolute;
		bottom: 0;
		width: 0;
		height: 0;
		border-style: solid;
		border-width: 50px 0 50px 100px;
		border-color: transparent transparent transparent #e15349;
		z-index: 2;
	}
	
	.letter {
		left: 20px;
		bottom: 0px;
		position: absolute;
		width: 160px;
		height: 60px;
		background: white;
		z-index: 1;
		overflow: hidden;
		-webkit-transition: .4s .2s;
		-moz-transition: .4s .2s;
		transition: .4s .2s;
		
		.letter-border {
			height: 10px;
			width: 100%;
      background: repeating-linear-gradient(
        -45deg,
        #cb5a5e,
        #cb5a5e 8px,
        transparent 8px,
        transparent 18px
      );
		}
		
		.letter-title {
			margin-top: 10px;
			margin-left: 5px;
			height: 10px;
			width: 40%;
			background: #cb5a5e;
		}
		.letter-context {
			margin-top: 10px;
			margin-left: 5px;
			height: 10px;
			width: 20%;
			background: #cb5a5e;
		}
		
		.letter-stamp {
			margin-top: 30px;
			margin-left: 120px;
			border-radius: 100%;
			height: 30px;
			width: 30px;
			background: #cb5a5e;
			opacity: 0.3;
		}
	}
}

.shadow {
	position: absolute;
	top: 200px;
	left: 50%;
	width: 400px;
	height: 30px;
	transition: .4s;
	transform: translateX(-50%);
	-webkit-transition: .4s;
	-webkit-transform: translateX(-50%);
	-moz-transition: .4s;
	-moz-transform: translateX(-50%);
	
	border-radius: 100%;
	background: radial-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.0), rgba(0,0,0,0.0));
}

	.letter-image.display {
		.animated-mail {
			transform: translateY(50px);
			-webkit-transform: translateY(50px);
			-moz-transform: translateY(50px);
		}
		
		.animated-mail .top-fold {
			transition: transform .4s, z-index .2s;
			transform: rotateX(180deg);
			-webkit-transition: transform .4s, z-index .2s;
			-webkit-transform: rotateX(180deg);
			-moz-transition: transform .4s, z-index .2s;
			-moz-transform: rotateX(180deg);
			z-index: 0;
		}
		
		.animated-mail .letter {
			height: 180px;
		}
		
		.shadow {
			width: 250px;
		}
	}
			}
		}
		.form{
			display: flex;
    		justify-content: center;
    		align-items: flex-end;
			form{
				width: 100%;
            	border-radius: 10px;
            	padding: 20px;
            	color: #C3F672;
				border: 1px solid #C3F672;
    			box-shadow: 1px 1px 4px #C3F672;
				margin-bottom: 65px;
				h3{
					font-family: 'Amsterdam Four_ttf';
					font-size: 40px;
					margin-bottom: 40px;
				}
            	.button{
                	text-align: center;
                	button{
						border: 1px solid #C3F672;
    					box-shadow: 1px 1px 4px #C3F672;
						color: white;
                    	margin: 10px;
                	}
            	}
        	}
		}
    }
}


</style>
