<template>
  <main>
    

    
      <PagPrincipal/>
      <PagCard/>
      <PagPhotosGym/>
      <PagPhotosSmall/>  
    
    
    <!--
      <PagTreiner/>
    -->

    
    <PagCardPrecos/>
    <PagContact/>
    <PagImc/>
    <PagProdutcs/> 
    <PagProductsSmall/>
    <PagMap/>  
  
  
  
  </main>
</template>

<script>
  import PagCard from './componentsMain/PagCard.vue';
  import PagPrincipal from './componentsMain/PagHome.vue';
  import PagCardPrecos from './componentsMain/PagCardPrices.vue'
  import PagMap from './componentsMain/PagMap.vue'
  import PagImc from './componentsMain/PagImc.vue'
  import PagProdutcs from './componentsMain/PagProdutcs.vue';
  import PagContact from './componentsMain/PagContact.vue'
  import PagTreiner from './componentsMain/PagTreiner.vue'
  import PagPhotosGym from './componentsMain/PagPhotosGym.vue'
  import PagPhotosSmall from './componentsMain/PagPhotosSmall.vue'
  import PagProductsSmall from './componentsMain/PagProductsSmall.vue';
  
export default {
    name: 'Main',
    components: {
      PagCard,
      PagPrincipal,
      PagCardPrecos,
      PagMap,
      PagImc,
      PagProdutcs,
      PagContact,
      PagTreiner,
      PagPhotosGym,
      PagPhotosSmall,
      PagProductsSmall
    }
}
</script>

<style>

/* Estilização pad~rao de TITULOS */
  .title {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-flow: row wrap;
    height: auto;
    margin: 2.6rem auto;
    gap: 1.4rem;

  }
  .title span {
        padding: 1.25rem;
        background-color: #39b839;
        border-radius: 1.25rem;
        color: white;
        font-weight: bold;
        margin-left: 0.625rem;
    }
    .title h2 {
        font-size: 1.6rem;
        font-weight: 500;
        margin-bottom: 1.2rem;
    }
    @media screen and (max-width: 33.75rem){
        .title {
            justify-content: center;
            align-items: center;
            width: 100%;
            margin: 1.25rem auto;
            gap: 0.5rem;
        } 
    }

    @media screen and (max-width: 12.5rem) {
        #span1 {
        display: none;
        }
        .titulo h2{
            font-size: 1.2rem;
        }
    }

    /* Efeitos de HOVER */
</style>