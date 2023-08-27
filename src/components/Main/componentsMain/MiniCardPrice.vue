<template>
    <div id="card-principal">
        <div id="prices">
            <span v-show="card.recomendad" id="pillRecomended">RECOMENDADO</span>
            <h2 id="titlePrice">{{ card.title }}</h2>
            
            
            <div id="price">R$ {{ card.price }}</div>
        </div>
        <div id="points">
            <P><i class="fa-solid fa-check fa-xl" style="color: #39b547;"></i>  {{ card.topic1 }}</P>
            <P><i class="fa-solid fa-check fa-xl" style="color: #39b547;"></i>  {{ card.topic2 }}</P>
            <P><i class="fa-solid fa-check fa-xl" style="color: #39b547;"></i> {{ card.
            topic3 }}</P>
            <P><i class="fa-solid fa-check fa-xl" style="color: #39b547;"></i>  {{ card.topic4 }}</P>

            <!--Card.check é uma verificação se o topico 5 vai ser exibido, se true, então é necessário outra verificação, o card.confirm. True para o simbolo de check e false para o simbolo de cancel-->

            <P v-if="card.check">
                <i v-show="card.confirm" class="fa-solid fa-check fa-xl" style="color: #39b547;"></i> 
                <i v-if="!card.confirm" class="fa-solid fa-xmark fa-lg" style="color: #dd3636;"></i>  {{ card.topic5 }}
            </P>

            <p v-if="card.estudante"><i class="fa-solid fa-circle-exclamation fa-lg" style="color: #f0e247;"></i>  Apenas Estudantes!</p>

        </div>
        
        <div id="botaoAdd"><a href="https://web.whatsapp.com/send?phone=88999501040" target="_blank" id="nameButton">Obter</a></div>
    </div>
    
</template>

<script>
    export default {
        name: 'MiniCardprice',
        props: {
           card: Object,
           card: Boolean
        }
    }
</script>

<style scoped>
    #card-principal{
        height: 30rem;
        width: 20rem;
        border: 0.125rem solid black;
        margin: 0rem 2.5rem;
        border-radius: 0.75rem;
        position: relative;
        margin-bottom: 3rem;
    }

    #pillRecomended{
        background-color: rgb(57, 181, 71);
        color:azure;
        border-radius: 1.25rem;
        padding: 0.5rem 0.938rem;
        font-weight: bold;
        position: absolute;
        top: -5%;
        right: -5%;
    }

    #prices{
        position: relative;
        top: 0;
        background-color: #222;
        color: azure;
        height: 12.5rem;
        border-radius: 0.563rem 0.563rem 0.938rem 0.938rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 0.938rem;
    }

    #titlePrice{
        font-size: 1.3rem;
        font-weight: normal;
    }

    #price{
        font-size: 2.5rem;
        font-weight: bold;
    }

    #points{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 0.938rem;
        margin-top: 1.875rem;
        font-size: 1.1rem;
    }

    #botaoAdd{
        background-color: #222;
        color:azure;
        border-radius: 1.25rem;
        padding: 0.625rem 0.875rem;
        font-weight: bold;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 12.5rem;
        position: absolute;
        margin: 0 auto;
        left: 18%;
        bottom:2%;
        margin-top: 0.625rem
    }

    #botaoAdd::before {
    content: "";
    border-radius: 1.25rem;
    background-color: #39B547;
    position: absolute;
    display: block;
    color: #fff;
    inset: 0;
    z-index: 0;
    transition: transform 300ms ease;
    transform-origin: 100%;
    transform: scaleX(0);   
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
    color: #fff;
}

@media screen and (max-width: 74.938rem) {
    #card-principal {
        margin-bottom: 2rem;
    }

    #botaoAdd {
        height: 3.2rem;
    }
}

@media screen and (max-width: 12.5rem) {
    #points {
        display: none
    }

    #prices {
        width: 100%;
        height: 100vh;
    }   
    
    #card-principal {
        width: 100%;
    }
}
</style>