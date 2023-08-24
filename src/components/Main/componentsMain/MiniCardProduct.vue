<template>
    <div id="set">
      <div class="card" >
        <div id="stars">
          <i class="fa-solid fa-star fa-lg" style="color: #39b547;"></i>
          <i class="fa-solid fa-star fa-lg" style="color: #39b547;"></i>
          <i class="fa-solid fa-star fa-lg" style="color: #39b547;"></i>
          <i class="fa-solid fa-star fa-lg" style="color: #39b547;"></i>
          <i class="fa-solid fa-star fa-lg" style="color: #39b547;"></i>
        </div>
        <img src="/img/products/whey.jpg" alt="">
        <div id="title"> Whey Protein - 2Kg </div>
        <div id="prices">
          <span id="priceNew">R$35,00</span>
          <span id="btnComprar"><a href="">Comprar</a></span>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
      name: 'MiniCardProduct',
      methods: {
        mostrarBtnComprar(){
          let card = document.querySelector('.card')
          let btnComprar = document.querySelector('#btnComprar')
  
          btnComprar.classList.add('d-block')
          btnComprar.classList.remove('d-none')
          card.classList.add('opacidade')
        },
  
        esconderBtnComprar(){
          let card = document.querySelector('#card')
          let btnComprar = document.querySelector('#btnComprar')
  
          card.classList.remove('opacidade')
          btnComprar.classList.add('d-none')
          btnComprar.classList.remove('d-block')
        }
      }
  }
  </script>
  
  <style scoped>
  
  a {
    text-decoration: none;
    color: white;
  }
 
  img {
    width: 150px;
  }
  
  #set {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    gap: 20px;
  }
  .card {
    transition: 0.6s;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 20px 30px;
    gap: 20px;
    color: #222;
    box-shadow: 6px 6px 10px rgba(0, 0, 0, 0.295);
  }
  
  #title {
    font-size: 1.4rem;
  }
  
  #prices {
    display: flex;
    justify-content: space-between;
    width:90%;
    align-items: center;
    gap: 15px;
  }
  
  #priceNew {
    font-size: 1.4rem;
    color: #39b547;
    font-weight: 700;
  }
  
  #stars {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-flow: row nowrap;
    gap: 4px;
    margin-bottom: 10px;
  }
  
  #btnComprar {
        
    background-color: #39b547;
    color: #fff;
    padding: 15px;
    border-radius: 20px;
    font-size: 1.1rem;
    opacity: 1;
    cursor: pointer;
    font-weight: 700;
  }
  
  #btnComprar:hover{
    box-shadow: 0px 0px 12px rgba(0, 0, 0, 0.623);
  }
  
  </style>
  