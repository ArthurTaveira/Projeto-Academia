<template>
    <footer>
        <!--IMG-->
        <img id="imgLogo" src="/img/logo/imgRedondaLogoPrincipal.png" alt="">

        <!--LISTAS-->
        <div class="list">
            <div class="listFooter">
                <h3>TopFitness</h3>
                
                <ul>
                    <li><a href="../Main/#pagHome" target="_self">> Home</a></li>
                    <li><a href="">> Treinadores</a></li>
                    <li><a href="../Main/#pagMap" target="_self">> Local</a></li>
                    <li><a href="../Main/#pagCardPrices" target="_self">> Preços</a></li>
                </ul>
            </div>
            <div class="listFooter">
                <h3>Extras</h3>
                <ul>
                    <li><a href="../Main/#pagImc" target="_self">> Imc</a></li>
                    <li><a href="">> Local</a></li>
                    <li><a href="../Main/#slider" target="_self">> Produtos</a></li>
                </ul>
            </div>
            
            <div class="listFooter">
                <h3 >Desenvolvedor</h3>
                <ul>
                    <li><a href="https://www.instagram.com/_dev.arthur/" target="_blank"> <i class="fa-brands fa-instagram fa-sm" style="color: #ffffff;"></i> Instagram</a></li>

                    <li><a href="https://www.linkedin.com/in/arthurtaveira/" target="_blank"> <i class="fa-brands fa-linkedin fa-sm" style="color: #ffffff;"></i> Linkedin</a></li>

                    <li><a href="https://web.whatsapp.com/send?phone=88999619865" target="_blank"> <i class="fa-brands fa-whatsapp fa-sm" style="color: #ffffff;"></i> Whatsapp</a></li>
                </ul>
            </div>
        </div>

        <!--Div que contem imagens e redes sociais-->
        <div class="ImgAndContact">
            <!--IMAGENS-->
            <div>
                <div>
                    
                    <img  class="imgGallery" src="/img/logo/imagemimagem.png" alt="">
                    <img class="imgGallery" src="/img/logo/imagemimagem.png" alt="">
                    <img class="imgGallery"  src="/img/logo/imagemimagem.png" alt="">
                </div>
                <div>
                    <img class="imgGallery" src="/img/logo/imagemimagem.png" alt="">
                    <img class="imgGallery" src="/img/logo/imagemimagem.png" alt="">
                    <img class="imgGallery" src="/img/logo/imagemimagem.png" alt="">
                </div>
            </div>
            <!--CONTATO E REDES SOCIAIS-->
            <div>
                <div id="insta-whats-local">
                    <div><a href="https://www.instagram.com/_top_fitness/" target="_blank"><i class="fa-brands fa-instagram fa-2xl" style="color: #ffffff;"></i></a></div>

                    <div><a href="https://web.whatsapp.com/send?phone=88999501040" target="_blank"><i class="fa-brands fa-whatsapp fa-2xl" style="color: #ffffff;"></i></a></div>

                    <div><a href=""><i class="fa-solid fa-location-dot fa-2xl" style="color: #ffffff;"></i></a></div>
                </div>
                <div id="botao-add"><span id="textButton">CONTATO</span></div>
            
            
            </div>
        </div>
    </footer>
</template>

<script>
    export default{
        name: 'Footer'
    }
</script>

<style scoped>
    footer{
        background-color: rgb(39, 39, 39);
        width: 100%;
        padding: 1.25rem;

        display: flex;
        flex-flow: row wrap;
        justify-content: space-evenly;
        align-items: center;

        color: rgb(170, 170, 170);
    }

    ul {
        list-style: none;
    }

    ul li {
        margin: 0.5rem 0rem;
    }

    a {
        text-decoration: none;
        color: rgb(170, 170, 170);
    }

    a:hover {
        transition: 0.4s;
        color: #39B547;
    }

    .ImgAndContact {
        display: flex;
        flex-flow: row wrap;
        gap: 3.125rem;
        justify-content: center;
        align-items: center;
    }
    
    #imgLogo {
        height: 7.5rem;
        margin-bottom: 1.875rem;
    }

    /* LISTAS */

    .list {
        display: flex;
        justify-content: center;
        align-items: start;
        gap: 2.5rem;
        flex-flow: row wrap;
    }

    .listFooter {
        font-size: 1.3rem;
    }

    /*IMAGENS */
    .imgGallery {
        width: 4.5rem;
    }

    /* REDES SOCIAIS */

    #insta-whats-local {
        display: flex;
        flex-flow: row nowrap;
        gap: 0.625rem;
        justify-content: center;
        margin-bottom: 1.875rem;
        gap: 1.875rem;
        
    }

    /* BTN */

    #botao-add{
        background-color: #39B547;
        color:azure;
        border-radius: 1.25rem;
        padding: 0.625rem 0.875rem;
        font-weight: bold;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 12.5rem;
        position: relative;
    
    }

    #botao-add::before {
    content: "";
    border-radius: 1.25rem;
    background-color: #fff;
    position: absolute;
    display: block;
    color: #fff;
    inset: 0;
    z-index: 0;
    transition: transform 300ms ease;
    transform-origin: 100%;
    transform: scaleX(0);
    
}

#botao-add:hover::before {
    transform: scaleX(1);
    transition-duration: 500ms;
    transform-origin: 0%;
    border-radius: 1.25rem;
    color: white;
}

#botao-add:hover{
    color: #39B547;
    transition: 0.3s;
    border-radius: 1.25rem;
}

#textButton{
    z-index: 2;
    background-color: transparent;
}

@media screen and (max-width: 68.75rem){
    .ImgAndContact {
        
        margin: 2.5rem;
    }

    .imgGallery {
        width: 6rem;
    }
}
</style>