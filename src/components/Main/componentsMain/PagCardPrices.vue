<template>
    <div class="title">

        <h2>Planos de Assinatura</h2>
        <div>
            <span id="span1">TopFitness</span>
            <span id="span2">Preços</span>
        </div>

    </div>

    <div id="pagCardPrices" class="container">
        <MiniCardPreco :card="card1" class="item" />
        <MiniCardPreco :card="card2" class="item" />
        <MiniCardPreco :card="card3" class="item" />
    </div>

</template>

<script>
    import MiniCardPreco from './MiniCardPrice.vue';

    export default {
        name: "PagCardPrices",
        components: {
            MiniCardPreco
        },
        data(){
            return{
                card1: {
                },
                card3: {
                },
                card2: {
                },

            }
        },
        mounted(){
            fetch('/data/Prices.json')
            .then((res)=> res.json())
            .then((Prices)=> {
                    this.card1 = Prices.card1
                    this.card2 = Prices.card2
                    this.card3 = Prices.card3
            })
        }
    }
</script>

<style scoped>
    #pagCardPrices{
        display: flex;
        align-items: center;
        justify-content: center;
        flex-flow: row wrap;
        width: 100%;
    }
    .item {
    transition: 0.35s;
    cursor: pointer;
  }

  .title {
    margin-top: 5rem
  }
  
  .container:hover > :not(:hover) {
    opacity: 0.4;
    transform: scale(0.9);
  }
    @media screen and (max-width: 12.5rem) {
        #PagCardPrices {
            display: none;
        }
    }

</style>