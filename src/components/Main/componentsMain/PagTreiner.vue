<template>
    <div>Treinadores</div>
    <div id="PagCardTreiner" class="container">
        <MiniCardPreco class="item"/>
        <MiniCardPreco class="item"/>
        <MiniCardPreco class="item"/>
    </div>
</template>

<script>
import MiniCardPreco from './MiniCardTreiner.vue'
    export default{
        name: 'PagTreiner',
        components: {
            MiniCardPreco 
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
        height: 100vh;
        
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