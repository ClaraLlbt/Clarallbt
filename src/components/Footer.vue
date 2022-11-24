<template>
    <footer id="footer" class="container-fluid">
        <div class="row networks-icons"> 
            <div class="col-md-2 icons">
                <div class="col-md-2 linked"><a href="https://www.linkedin.com/in/chltc/"><i class="bi bi-linkedin"></i></a></div>
                <div class="col-md-2 instagram"><a href="https://www.instagram.com/kala__ikebana/"><i class="bi bi-instagram"></i></a></div>
            </div> 
        </div>
        <div class="row copyright">
            <div class="col-md-6">
                <p>{{this.message + this.currentYear + " " + this.name + " - "}}<i class="bi bi-geo-alt-fill"></i> {{ this.location}}</p>
            </div>
        </div>
    </footer>
</template>

<script>
    export default {
        name: "Footer",
        data(){
            return{
                currentYear: "",
                message: "Copyright©",
                name: "Clara Laliberté",
                location: "Boulogne-sur-Mer"
            }
        },
        mounted(){
            this.Copyright(),
            this.networksIcons()
        },
        methods:{
            Copyright(){
                this.currentYear = new Date().getFullYear();
            },
            networksIcons(){
                const bottomFooter = document.querySelector('#footer')
                const icons = document.querySelector('.icons')

                window.addEventListener('scroll', () => { 
                    const { clientHeight } = document.documentElement;
                    const topElementToTopViewport = bottomFooter.getBoundingClientRect().bottom;
                    if(clientHeight == topElementToTopViewport.toFixed()){
                        icons.classList.add('active')
                    }
                })
            }
        }
    }
</script>

<style lang="scss" scoped>
footer{
    background: #AF6EEF;
    color:darkslategrey;
    .row.networks-icons{
        justify-content: center;
        overflow: hidden;
        .icons{
            justify-content: center;
            display: inline-flex;
            transform: translateY(42px);
            opacity: 0;
            transition: transform 2s ease-in-out, opacity 0.6s ease-in-out;
            div{
                text-align: center;
                font-size: 25px;
                margin: 10px;
                a{
                    &:hover{
                        background: none;
                        color: white;
                    }
                }
            }
        }
        .icons.active{
            transform: translateY(0);
            opacity: 1;

        }
    }
    .row.copyright{
        justify-content: center;
        p{
            padding: 10px;
            text-align: center;
            border-top: 1px solid darkslategrey;
        }
    }

}
</style>