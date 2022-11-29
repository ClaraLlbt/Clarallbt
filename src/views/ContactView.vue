<template>
    <div id="contact" class="contact">
        <NavbarVue />
        <HdrBanner />

        <div class="row contact-form">
            <div class="col-12 col-md-6 span-txt">
                <h2>Contactez-moi !</h2>
                <span class="span-1">Vous souhaitez discuter de mes motivations ? Je vous invite à me contacter. Vous pouvez télécharger mon cv ou utiliser le formulaire.</span>
                <div class="col-12 btn-dl-cv">
                    <a href="/ClaraLaliberT/lib/web/CV_LALIBERTE_CLARA.pdf" download="">
                        <button type="button" class="btn btn-light"><i class="bi bi-file-pdf"></i> Télécharger mon CV</button>
                    </a>
                </div>
                <span class="span-2">A Bientôt !</span>
            </div>
            <div class="col-12 col-md-6 form">
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
                        <button id="sendBtn" @click="sendEmail()" type="submit" value="Send Email" class="btn btn-light">Envoyer</button>
                    </div>
                </form>
            </div>
        </div>

    </div>
    
    <FooterVue />
</template>

<script>
import emailjs from "emailjs-com"
import NavbarVue from '../components/Navbar.vue';
import HdrBanner from '../components/HdrBanner.vue';
import FooterVue from '../components/Footer.vue';
    export default {
        name: 'contact',
        components: { HdrBanner, FooterVue, NavbarVue },
        data(){
            return{
                email: '',
                message: '',
            }
        },
        mounted(){
            this.slideTxt()
        },
        methods: {
            slideTxt(){
                const spanTxt = document.querySelector('.span-1');
                const spanTxt2 = document.querySelector('.span-2')
                const btnDlCv = document.querySelector('.btn-dl-cv');

                spanTxt.classList.add('active');
                spanTxt2.classList.add('active2');
                btnDlCv.classList.add('active3');
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
#contact{
    #navbar{
        button{ display: none !important}
        .menu{ display: none;}
        .menu-contact{ display: block !important}
    }
    .contact-form{
        width: 100%;
        height: 100%;
        margin: auto;
        position: absolute;
        top: 10%;
        color: white;
        align-content: space-around;
        padding-bottom: 150px;
        .span-txt{
            text-align: center;
            display: grid;
            span{ font-size: 20px;}
            span, .btn-dl-cv{
                transform: translateX(-900px);
                opacity: 0;
                transition: transform 2s ease-in-out, opacity 0.6s ease-in-out;
            }
            .span-1.active, .span-2.active2, .btn-dl-cv.active3{
                transform: translateX(0);
                opacity: 1;
            }
        }
        form{
            background: white;
            border-radius: 10px;
            padding: 20px;
            color: #485665;
            .button{
                text-align: center;
                button{
                    margin: 10px;
                }
            }
        }
    }
}
</style>