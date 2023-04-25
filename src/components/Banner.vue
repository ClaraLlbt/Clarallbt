<template>
    <div id="hdrBanner">
        <div class="banner">
            <img src="../assets/banner.png" alt="">
        </div>

        <div class="row home-title">
            <img class="profil-pic" src="../assets/ultrapic2.svg" alt="">
            
            <h1 id="animate_text" class="">Développeur web Junior</h1>

            <a class="scroll-link" href="#about">
		        <svg class="mouse" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 76 130" preserveAspectRatio="xMidYMid meet">
		            <g fill="none" fill-rule="evenodd">
			            <rect width="70" height="118" x="1.5" y="1.5" stroke="#FFF" stroke-width="3" rx="36"/>
			            <circle class="scroll" cx="36.5" cy="31.5" r="4.5" fill="#FFF"/>
		            </g>
	            </svg>
	        </a>
        </div>

    </div>
</template>

<script>
    export default {
        name: 'Banner',
        mounted(){
            this.animateTxt()
        },
        methods: {
            animateTxt(){
                const txt = document.getElementById("animate_text");

                const splitTxt = txt.innerText.split("");
  
                txt.innerText = "";
                let i = 0;
                setInterval(function () {
                    addLetters();
                }, 100);
                function addLetters() {
                    if (i < splitTxt.length) {
                        txt.innerHTML += splitTxt[i];
                        i++;
                    }
                }
            }

        },
    }
</script>

<style lang="scss" scoped>
#hdrBanner{
    max-width: 100%;
    height: 100vh;
    .banner img {
        object-fit: cover;
        height: 100vh;
        width: 100%;
        filter: blur(1px);
    }
    .home-title{
        display: flex;
        justify-content: center;
        position: absolute;
        height: 100%;
        width: 100%;
        top: 0;
        color: white;
        align-content: space-evenly;
        .profil-pic{ 
            width: 100%;
            height: 32%;
        }
        h1{ 
            font-size: 60px;
            text-align: center;
            font-family: 'Amsterdam Four_ttf';
        }
        .scroll-link{
            text-align: center;
        }
        .mouse {
            max-width: 40px;
	        width: 100%;
	        height: auto;
        }
        .scroll {
	        animation-name: scroll;
	        animation-duration: 1.5s;
	        animation-timing-function: cubic-bezier(0.650, -0.550, 0.250, 1.500);
	        animation-iteration-count: infinite;
	        transform-origin: 50% 20.5px;
            will-change: transform, opacity;
	        opacity: 1;
        }
        @keyframes scroll {
            0%, 20% {
		        transform: translateY(0) scaleY(1);
	        }
	        100% {
		        transform: translateY(36px) scaleY(2);
		        opacity: 0;
	        }
        }
        @media (max-width: 550px) {
            height: 100%;
            width: 100%;
            top: 0;
            left: 0;
            margin: auto;
            h1, a{
                text-align: center;
            }
            h1{ font-size: 30px;}
            a{ 
                left: 0;
                font-size: 30px;
                width: 90%;
                place-self: center; 
            }
        }
    }
}
</style>