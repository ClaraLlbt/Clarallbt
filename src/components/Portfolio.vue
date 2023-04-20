<template>
    <div class="container-fluid portfolio-ctr">

        <div class="row">
            <div class="col-lg-6 cards-grp">
                <!--Card 1-->
                <div class="card">
                     <img src="../assets/images/reservia.png" class="card-img-top" alt="...">
                    <div class="card-body">
                        <h5 class="card-title">Reservia</h5>
                        <h6 class="card-subtitle">Transformer une maquette en site web avec HTML 5 et CSS 3</h6>
                        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>

                        <div class="row langages">
                            <div class="col-lg-4 html">HTML 5</div>
                            <div class="col-lg-4 css">CSS 3</div>
                        </div>
                    </div>
                </div>
                <!--Card 2-->
                <div class="card">
                     <img src="../assets/images/OhMyFood.png" class="card-img-top" alt="...">
                    <div class="card-body">
                        <h5 class="card-title">OhMyFood!</h5>
                        <h6 class="card-subtitle">Dynamiser une page web avec des animations CSS</h6>
                        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>

                        <div class="row langages">
                            <div class="col-lg-4 html">HTML 5</div>
                            <div class="col-lg-4 css">CSS 3</div>
                        </div>
                    </div>
                </div>
                <!--Card 3-->           
                <div class="card">
                     <img src="../assets/images/reservia.png" class="card-img-top" alt="...">
                    <div class="card-body">
                        <h5 class="card-title">Piiquante</h5>
                        <h6 class="card-subtitle">Construire une API sécurisée pour une application</h6>
                        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>

                        <div class="row langages">
                            <div class="col-lg-4 html">HTML 5</div>
                            <div class="col-lg-4 css">CSS 3</div>
                        </div>
                    </div>
                </div>
                
               
            </div>
            <div class="col-lg-6">
                
            </div>
        </div>

    </div>
</template>

<script>
    export default {
        name: 'Portfolio'
    }
</script>

<style lang="scss" scoped>
.portfolio-ctr{
    margin: 30px;
    .row{
        .cards-grp{
            height: 100vh;
            overflow: auto;
            display: grid;
            justify-content: center;
            margin: 10px;
            &::-webkit-scrollbar {
                display: none; /* for Chrome, Safari, and Opera */
            }
            //General Cards Design
            .card{
                width: 60%;
                margin: 15px auto;
                &:hover{ cursor: crosshair; }
                .card-body{
                    .langages{
                        .html{
                            color: white;
                            background: #F75421;
                            opacity: 50%;
                            margin: 5px;
                            text-align: center;
                        }
                        .css{
                            color: white;
                            background: #2790C9;
                            opacity: 50%;
                            margin: 5px;
                            text-align: center;
                        }
                    }
                }
            }
        }
    }
}
</style>