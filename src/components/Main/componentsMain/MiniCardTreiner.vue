<template>
    
    <div id="cardPrincipal">
        <!-- <div id="local-img">
            <img id='img' src="/img/logo/imagemimagem.png" alt="">
        </div>
        <div id="local-texts">
            <div>NOME</div>
            <div>PEQUENA FRASE</div>
        </div> -->
        <img :src="treiner.img" alt="">
        <span>{{ treiner.nome }}</span>
    </div>
</template>
<script>
    export default {
        name: 'PagTreiner',
        props:{
            treiner: Object
        }
    }
</script>
<style scoped>
        #cardPrincipal{
        height: auto;
        width: auto;
        margin: 0 50px 50px 50px;
        border-radius: 0.75rem;
        position: relative;

        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    #cardPrincipal span {
        color: #222;
        font-size: 2.5rem;
        font-weight: 700;
    }

    .title {
        margin: 0;
    }
/* 
    #local-img{
        background-color: rgb(105, 228, 24);
        height: 21.875rem;
        width: 18.125rem;
        border-radius: 1.25rem;
        margin: 0 auto;
        margin-top: 0.063rem;

        display: flex;
        align-items: center;
        justify-content: center;

    } */

    img {
        border-radius: 50%;
        width: 300px;
        height: 300px;
        animation:  moveUpDown 3s infinite ease-in-out
    }

    #local-texts{
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
        gap: 0.063rem;
        margin-top: 1.875rem;
    }

    #img {
        width: 12.5rem;
        animation: moveUpDown 3s infinite ease-in-out
    }

    
  @keyframes moveUpDown {
    0%, 100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-0.5rem);
    }
  }

  @media screen and (max-width: 33.75rem){
       
       #card-principal{
            margin: 0;
           margin-bottom: 1.2;
       }
       }



</style>