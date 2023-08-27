<script >
  import MiniCard from './MiniCard.vue';
  export default {
    name: 'PagCard',
    components: {
    MiniCard
    },
    data(){
      return{
        card1: {},
        card2: {},
        card3: {},
        card4: {},
      }
    },
    mounted(){
      fetch('/data/Benefits.json')
      .then((res)=> res.json())
      .then((cards)=> {
        this.card1 = cards.card1
        this.card2 = cards.card2
        this.card3 = cards.card3
        this.card4 = cards.card4
      })
    }
  }
</script>

<template>
  
    <div id="divBenefits">
     

      <q cite=''>" Movimente seu corpo, discipline sua mente! "</q>

      <div class="title">

        <h2>Por quê Treinar?</h2>

        <div>
          <span id="span1">TopFitness</span>
            <span id="span2">Benefícios</span>
        </div>

      </div>
      
      
      <div id="setCards">
        <div class="setCards2">
          <MiniCard v-bind:card="card1"/>
          <MiniCard v-bind:card="card2"/>
        </div>
        <div class="setCards2">
          <MiniCard v-bind:card="card3"/>
          <MiniCard v-bind:card="card4"/>
        </div>
      </div>
    </div>
</template>

<style scoped>

/* Configuração de display flex */

#divBenefits, #title, #setCards, .setCards2, q{
  display: flex;
}



/*Configurações Gerais */

#divBenefits{
    align-items: center;
    width: 100%;
    flex-direction: column;
    justify-content: center;
    
  }

    /* Citação */

    q{
    width: 50%;
    font-size: 1.9rem;
    font-weight: normal;
    margin-bottom: 1.25rem;
    color: #222;
    font-style: italic;
    cursor: pointer;
    position: relative;
    padding-bottom: 0.625rem;
    margin-bottom: 1.25rem;
    align-items: center;
    justify-content: center;
  }

  q::before {
    content: "";
    position: absolute;
    color: #fff;
    inset: 0;
    z-index: 0;
    transition: transform 500ms ease;
    transform-origin: 100%;
    transform: scaleX(0);
    border-bottom: 0.125rem solid #222;
}

 q:hover::before {
    transform: scaleX(1);
    transition-duration: 700ms;
    transform-origin: 0%;
    color: white;
}

/* Titulo da Pagina */

    .titulo {
        width: 79%;
    }

    /*Organização dos cards */

  #setCards{
    align-items: center;
    justify-content: center;
    flex-flow: row wrap;
    width: 100%;
    
  }

  /*Conjunto de dois cards */

  .setCards2 {
    flex-direction: row;
  }

  @media screen and (max-width: 68.75rem) {
    
    #divHome {
      height: auto;
    }
}
  @media screen and (max-width: 33.75rem) {
    
    .setCards2, #setCards, #divHome {
      align-items: center;
      justify-content: center;
    }

    .setCards2, #setCards{
      flex-direction: column;
    }

    q{
      font-size: 1.5rem;
    }
}



@media screen and (max-width: 12.5rem) {

   
  #setCards, .setCards2, q{
      width: 100%;
    }

    q {
      padding: 0.625rem 1.25rem;
      pointer-events: none;
      font-size: 1.4rem;
      margin-top: 1.875rem;
    }

  }
  
</style>
