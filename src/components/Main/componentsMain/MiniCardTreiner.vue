<template>
    
    <div id="card-principal">
        <div id="local-img">
            <img id='img' src="/img/logo/imagemimagem.png" alt="">
        </div>
        <div id="local-texts">
            <div>NOME</div>
            <div>PEQUENA FRASE</div>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'PagTreiner'
    }
</script>
<style scoped>
        #card-principal{
        height: 480px;
        width: 320px;
        border: 2px solid black;
        margin: 50px;
        border-radius: 0.75rem;
        position: relative;
    }

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
      transform: translateY(-1.25rem);
    }
  }



</style>