<template>
    <div id="pagMap">

        <div id="info">
            <img  id="img1" src="/img/logo/zyro-image.png" alt="">
            <p>Localização: <i class="fa-sharp fa-solid fa-location-dot fa-bounce fa-lg" style="color: #020202;"></i></p>
            <p>Lavras da mangabeira - <strong>CE</strong></p>
            <p>Rua José Linhares - <strong>Centro</strong></p>
            <P>Segunda a Sexta - 5:00 as 21:30</P>
            <p><strong>CEP:</strong> 63300-000</p>
            <div id="botaoAdd"><span id="nameButton">Contato</span></div>
        </div>

        <div class="mapResponse">
            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3280.1475908777766!2d-38.96680128016973!3d-6.7552994166578655!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x7a3977738992e9b%3A0x1c1fc2e94e972f1a!2sFitness%20Academia!5e0!3m2!1spt-BR!2sbr!4v1691848873201!5m2!1spt-BR!2sbr" style="border:0;" allowfullscreen="" loading="lazy"  referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div>
    </div>

    <div class="bubble"></div>
</template>

<script>
    export default {
        name: 'PagMap'
    }
</script>

<style scoped>

/* Informações */

    #info{
        position: relative;
        display: flex;
        flex-flow:column nowrap;
        font-size: 1.1rem;
        gap: 0.2rem;
    }

    #img1{
        width: 25rem;
        margin-bottom: 0.625rem;
    }

    /* Geral */

    #pagMap {
        display: flex;
        align-items: center;
        justify-content: space-around;
        flex-flow: row wrap;
        gap: 4.375rem;
        max-height: 31.25rem;
        position: relative;
        padding: 2.5rem 1rem;
        max-width: 81.25rem;
        margin: 0 auto 3rem auto;
    }

    /* btn contato */

    #botaoAdd{
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
        margin-top: 0.625rem;
      

    }

    #botaoAdd::before {
    content: "";
    background-color: #222;
    position: absolute;
    display: block;
    color: #fff;
    inset: 0;
    z-index: 0;
    transition: transform 300ms ease;
    transform-origin: 100%;
    transform: scaleX(0);
    border-radius: 1.25rem;
    
}

#botaoAdd:hover::before {
    transform: scaleX(1);
    transition-duration: 500ms;
    transform-origin: 0%;
    border-radius: 1.25rem;
    color: white;
}

#botaoAdd:hover{
    color: #fff;
    transition: 0.3s;
    border-radius: 1.25rem;
}

#nameButton{
    z-index: 2;
    background-color: transparent;
}

    /* Map */
    .mapResponse{
        overflow:hidden;
        padding-bottom:16.25%;
        position:relative;
        height:63vh;
        width: 36.25rem;
        text-align: center;
    }

    .mapResponse iframe{
        left:0;
        top:0;
        height:100vh;
        width:100%;
        position: absolute;
        text-align: center;
    }
    
/*Bolha que empurrará o footer */
.bubble {
    width: 100%;
    height: 21.875rem;
    background-color: transparent;
    display: none;
}

@media screen and (max-width: 68.25rem) {

    #pagMap {
        height: auto;
    }
    #info {
        align-items: center;
    }

    #img1 {
        width: 22rem;
    }

    .bubble {
        display: block;
    }

    .mapResponse {
        margin: 0 1rem;
    }
}
</style>