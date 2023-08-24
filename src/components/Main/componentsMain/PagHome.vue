<template>
    <div id="pagHome">
        <atropos-component class="my-atropos">
            <img id="imgMain" src="/img/logo/imgCompleta2.0Transparet.png" alt="Imagem escrito o nome da academia, TopFitness, a palavra top Escrita em preto e a palavra Fitness escrita em Verde claro">
        </atropos-component>
        
        <img src="/img/logo/imgFraseRedonda.png" id='imgTelaPequena' alt="Imagem escrito o nome da academia, TopFitness, a palavra top Escrita em preto e a palavra Fitness escrita em Verde claro">

    </div>
    <i id='arrow' class="fa-solid fa-arrow-down fa-bounce fa-2xl" style="color: #020202;"></i>
</template>

<script>
export default {
    name:'pagHome'
}
</script>

<style scoped>
    
    #pagHome {
        width: 100%;
        height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center; 
        max-width: 125rem;
        }
        
    #imgMain{
        background-color: #fff;
        border-radius: 1.25rem;
        padding: 1rem;
    }

    #arrow{
        position: absolute;
        bottom: 5%;
        left: 5%;
    }

    #imgTelaPequena{
        display: none;
        width: 100%;
    }

    @media screen and (max-width: 50rem){
        #imgMain {
            width: 31.25rem;
        }
    }

    @media screen and (max-width: 34.063rem){
        #imgMain {
            width: 25rem;
        }
    }

    @media screen and (max-width: 25rem){
        #imgMain {
            width: 18.75rem;
        }
    }

    @media screen and (max-width: 15.625rem){
        #imgMain {
            display: none;
        }

        #imgTelaPequena{
            display: flex;
        }
    }


</style>
