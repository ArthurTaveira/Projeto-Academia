<template>
    <div class="title">

        <h2>Personal Treiners</h2>

        <div>
            <span id="span1">TopFitness</span>
            <span id="span2">Treinadores</span>
        </div>

    </div>

    <div id="PagCardTreiner" class="container">
        <MiniCardPreco class="item" v-bind:treiner="treinerKerlon"/>
        <MiniCardPreco class="item" v-bind:treiner="treinerMenina"/>
        <MiniCardPreco class="item" v-bind:treiner="treinerEdigleuson"/>
    </div>
</template>

<script>
import MiniCardPreco from './MiniCardTreiner.vue'
    export default{
        name: 'PagTreiner',
        components: {
            MiniCardPreco 
        },
        data(){
            return{
                treinerKerlon: {
                    img : '/img/treiner/KerlonRedondo.png',
                    nome: 'Kerlon'
                },
                treinerMenina: {
                    img : '/img/treiner/SamiaRedonda.png',
                    nome: 'Samia'
                },
                treinerEdigleuson: {
                    img : '/img/treiner/GledsonRedondo.png',
                    nome: 'Gledson'
                },
            }
        }

    }
</script>

<style scoped>
        #PagCardTreiner{
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
  
  .container:hover > :not(:hover) {
    opacity: 0.4;
    transform: scale(0.9);
  }


</style>