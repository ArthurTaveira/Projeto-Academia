<script >
  import Main from './components/Main/Main.vue'
  import PagFooter from './components/Footer/Footer.vue'
  import BtnZap from './components/Main/componentsMain/PagBtnZap.vue'
  import PagHeader from './components/Header/Header.vue'
  
  import AtroposComponent from 'atropos/element';

  export default {
    name: 'App',
    components: {
      PagHeader,
      Main,
      BtnZap,
      PagFooter
    },
    data(){
      return{
      }
      
    },
    mounted(){
      customElements.define('atropos-component', AtroposComponent);
    }
  }
</script>

<template>

  <header>
    <PagHeader/>
  </header>

  <main>
    <Main/>
    <BtnZap/>
  </main>

  <footer>
    <PagFooter/>  
  </footer>
  
</template>

<style >
  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    font-family: 'Roboto', sans-serif
  }

</style>
