<template>
    <header >

    <!--NAV BAR PARA COMPUTADORES-->
   <nav id="nav1">
       <ul>
        <!--LOGO-->
            <img id="img" src="/img/logo/imgRedondaLogoPrincipal.png" alt="logo da academia top fitness">

            <!--ITEM 1 NAV (TOPFITNESS)-->

            <li class="dropdown" @mouseenter="mouseEntrou('menu1')" @mouseout="mouseSaiu">
                <a href="">TopFitness   
                    <i v-show="mostrarDown1" class="fa-solid fa-caret-down fa-lg" style="color: #ffffff;"></i>
                    <i v-show="mostrarUp1" class="fa-solid fa-caret-up fa-lg" style="color: #ffffff;"></i>
                </a>

                <div class="dropdownMenu">
                    <a href="../Main/#pagHome" target="_self">Início <i class="fa-solid fa-house fa-sm" style="color: #ffffff;"></i></a>

                    <a href="">Professores <i class="fa-solid fa-users fa-sm" style="color: #ffffff;"></i></a>

                    <a href="../Main/#pagMap" target="_self">Local <i class="fa-solid fa-location-dot fa-sm" style="color: #ffffff;"></i></a>
                    
                    <a href="../Main/#pagCardPrices" target="_self">Planos <i class="fa-solid fa-dumbbell fa-sm" style="color: #ffffff;"></i></a>
                </div>
            </li>

             <!--ITEM 2 NAV (EXTRA)-->
            <li class="dropdown"  @mouseenter="mouseEntrou('menu2')"  @mouseout="mouseSaiu">
                <a href="">Veja Mais  
                    <i v-show="mostrarDown2" class="fa-solid fa-caret-down fa-lg" style="color: #ffffff;"></i>
                    <i v-show="mostrarUp2" class="fa-solid fa-caret-up fa-lg" style="color: #ffffff;"></i>
                </a>

                <div class="dropdownMenu">

                    <a href="../Main/#divBenefits" target="_self">Benefícios <i class="fa-solid fa-hand-holding-heart fa-sm" style="color: #ffffff;"></i></a>

                    <a href="../Main/#pagImc" target="_self">IMC <i class="fa-solid fa-calculator fa-sm" style="color: #ffffff;"></i></a>

                    <a href="../Main/#slider" target="_self">Produtos <i class="fa-solid fa-prescription-bottle fa-sm" style="color: #ffffff;"></i></a>

                    <a href="../Main/#pagPhotos" target="_self">Fotos <i class="fa-solid fa-image fa-sm" style="color: #ffffff;"></i></a>

                </div>
            </li>

            <!--ITEM 3 NAV (DESENVOLVEDOR)-->
            <li class="dropdown" @mouseenter="mouseEntrou('menu3')"  @mouseout="mouseSaiu">
                <a href="" >Dev.Arthur  
                    <i v-show="mostrarDown3" class="fa-solid fa-caret-down fa-lg" style="color: #ffffff;"></i>
                    <i v-show="mostrarUp3" class="fa-solid fa-caret-up fa-lg" style="color: #ffffff;"></i>
                </a>

                <div class="dropdownMenu">
                    <a href="https://www.linkedin.com/in/arthurtaveira/" target="_blank">Linkedin <i class="fa-brands fa-linkedin fa-sm" style="color: #ffffff;"></i> </a>
                    <a href="https://www.instagram.com/_dev.arthur/" target="_blank">Instagram <i class="fa-brands fa-instagram fa-sm" style="color: #ffffff;"></i></a>
                    <a href="https://web.whatsapp.com/send?phone=88999619865" target="_blank">Whatsapp <i class="fa-brands fa-whatsapp fa-sm" style="color: #ffffff;"></i></a>
                </div>
            </li>

            <!--BOTAO CONTATO-->
            <li>
                <div id="botaoAdd"><span id="name-button">Contato</span></div>
            </li>
        </ul>
    </nav>

    <!--NAV BAR PARA CELULARES-->
    <nav id="nav2">

        <img id="img" src="/img/logo/imgRedondaLogoPrincipal.png" alt="logo da academia top fitness">

        <div id="botaoAdd"><span id="name-button">Contato</span></div>

        <i class="fa-solid fa-bars fa-lg" @click="collpaseNavBar" style="color: #ffffff;"></i>
    </nav>

    <!--COLLAPSE NAVBAR-->
    <div v-show="collapse">
        <ul id="collapseNavBar">
            <!--ITEM 1 NAV (TOPFINESS)-->

            <li class="dropdown" @click="collapseItem('item1')">
                    TopFitness 

                    <i v-show="mostrarDown1" class="fa-solid fa-caret-down fa-lg" style="color: #ffffff;"></i>

                    <i v-show="mostrarUp1" class="fa-solid fa-caret-up fa-lg" style="color: #ffffff;"></i>
                

            </li>

            <div class="listItems" v-show="collapseItem1">
                <a href="">Início <i class="fa-solid fa-house fa-sm" style="color: #ffffff;"></i></a>
                <a href="">Professores <i class="fa-solid fa-users fa-sm" style="color: #ffffff;"></i></a>
                <a href="">Local <i class="fa-solid fa-location-dot fa-sm" style="color: #ffffff;"></i></a>
                <a href="">Planos <i class="fa-solid fa-dumbbell fa-sm" style="color: #ffffff;"></i></a>
            </div>

            <!--ITEM 2 NAV (EXTRA)-->
            <li class="dropdown" @click="collapseItem('item2')">
                Veja Mais  
                    <i v-show="mostrarDown2" class="fa-solid fa-caret-down fa-lg" style="color: #ffffff;"></i>
                    <i v-show="mostrarUp2" class="fa-solid fa-caret-up fa-lg" style="color: #ffffff;"></i>
                

            </li>

            <div class="listItems" v-show="collapseItem2">
                <a href="">Benefícios <i class="fa-solid fa-hand-holding-heart fa-sm" style="color: #ffffff;"></i></a>
                <a href="">IMC <i class="fa-solid fa-calculator fa-sm" style="color: #ffffff;"></i></a>
                <a href="">Produtos <i class="fa-solid fa-prescription-bottle fa-sm" style="color: #ffffff;"></i></a>
                <a href="">Fotos <i class="fa-solid fa-image fa-sm" style="color: #ffffff;"></i></a>
            </div>

            <!--ITEM 3 NAV (DESENVOLVEDOR)-->
            <li class="dropdown"  @click="collapseItem('item3')">
                Dev.Arthur  
                    <i v-show="mostrarDown3" class="fa-solid fa-caret-down fa-lg" style="color: #ffffff;"></i>
                    <i v-show="mostrarUp3" class="fa-solid fa-caret-up fa-lg" style="color: #ffffff;"></i>
                

            </li>

            <div class="listItems" v-show="collapseItem3">
                <a href="">Linkedin   <i class="fa-brands fa-linkedin fa-sm" style="color: #ffffff;"></i> </a>
                <a href="">Instagram   <i class="fa-brands fa-instagram fa-sm" style="color: #ffffff;"></i></a>
                <a href="">Whatsapp   <i class="fa-brands fa-whatsapp fa-sm" style="color: #ffffff;"></i></a>
            </div>
            </ul>
        </div>

    </header>
</template>

<script>
    export default {
        name: 'Header',
        data(){
            return{

                //Direção das Setas conforme os cliques
                mostrarUp1: false,
                mostrarDown1: true,
                mostrarUp2: false,
                mostrarDown2: true,
                mostrarUp3: false,
                mostrarDown3: true,

                //gerenciar cliques e fazer os collpases(nav Bar, celular)

                collapse: false,
                collapseItem1: false,
                collapseItem2: false,
                collapseItem3: false,
            }
        },
        methods: {
            //METODO QUANDO O MOUSE ENTRAR
            mouseEntrou(e){
                if(e === 'menu1'){
                    this.mostrarUp1 = !this.mostrarUp1
                    this.mostrarDown1 = !this.mostrarDown1
                }
                if(e === 'menu2'){
                    this.mostrarUp2 = !this.mostrarUp2
                    this.mostrarDown2 = !this.mostrarDown2
                }
                if(e === 'menu3'){
                    this.mostrarUp3 = !this.mostrarUp3
                    this.mostrarDown3 = !this.mostrarDown3
                }
            },
            //METODO QUANDO O MOUSE SAIR
            mouseSaiu(){
                this.mostrarDown1 = true
                this.mostrarDown2 = true
                this.mostrarDown3 = true

                this.mostrarUp1 = false
                this.mostrarUp2 = false
                this.mostrarUp3 = false
            },

            collpaseNavBar(){
                this.collapse = !this.collapse
            },

            collapseItem(item){
                if (item === 'item1') {
                    this.collapseItem1 = !this.collapseItem1
                    this.mostrarDown1 = !this.mostrarDown1
                    this.mostrarUp1 = !this.mostrarUp1

                }
                if (item === 'item2') {
                    this.collapseItem2 = !this.collapseItem2
                    this.mostrarDown2 = !this.mostrarDown2
                    this.mostrarUp2 = !this.mostrarUp2

                }
                if (item === 'item3') {
                    this.collapseItem3 = !this.collapseItem3
                    this.mostrarDown3 = !this.mostrarDown3
                    this.mostrarUp3 = !this.mostrarUp3

                }
            }
        }
    }
</script>

<style scoped>

/* FOI USADA A CLASSE PADRÂO DO FONT AWESOME PARA CRIAR UMA MARGEM */
.fa-solid{
    margin-left: 0.313rem;
}

/*Configuraões de Header */

header {
    width: 100%;
    font-size: 1.1rem;
    max-width: 125rem;
    position: fixed;
    top: 0;
    z-index: 999;
}

    /*Config Flex */

 nav, ul, #botaoAdd, #collapseNavBar, .listItems{
    display: flex;
 }

/*CONFIGURAÇÕES DO 1º NAV */
#img {
    width: 4.375rem;
}

nav{
    background-color: #333;
    width: 80%;
    margin: 0 auto;
    align-items: center;
    justify-content: space-evenly;
    

    padding: 0.125rem 0rem;
    border-radius: 0rem 0rem 0.375rem 0.375rem;

    box-shadow: 0.063rem 0.063rem 0.125rem rgba(0, 0, 0, 0.315);
}

ul {
    align-items: center;
    justify-content: space-evenly;
    width: 100%;
}

nav li{
    display: inline-block;
}

nav li a{
    display: inline-block;
    color: white;
    text-decoration: none;
    padding: 0.938rem;
}

nav li a:hover{
    background-color: #39B547;
    transition: .4s;
    border-radius: 0.938rem;
}

.dropdownMenu{
    position: absolute;
    display: none;
}

.dropdown{
    cursor: pointer;
    color: #fff
}
.dropdownMenu a:hover{
    border-radius: 0rem;
}

.dropdownMenu a{
    display: block;
    background-color: #333;
    color: #fff;
    width: 10rem;
    transition: 0.4s;
}

.dropdown:hover .dropdownMenu{
    display: block;
    transition: 0.4s;
}

/* BOTAO CONTATO */
#botaoAdd{
        background-color: white;
        color: #222;
        border-radius: 1.25rem;
        padding: 0.625rem 0.875rem;
        font-weight: bold;
        font-size: 1rem;
        align-items: center;
        justify-content: center;
        width: 9.375rem;
        position: relative;

}



#botaoAdd::before {
    content: "";
    border-radius: 1.25rem;
    background-color: #39B547;
    position: absolute;
    display: block;
    color: #fff;
    inset: 0;
    z-index: 0;
    transition: transform 300ms ease;
    transform-origin: 100%;
    transform: scaleX(0);
}

#botaoAdd:hover::before {
    transform: scaleX(1);
    transition-duration: 500ms;
    transform-origin: 0%;
    border-radius: 1.25rem;
    color: white;
}

#botaoAdd:hover{
    color: #fff;
    transition: 0.3s;

    box-shadow: 0rem 0rem 0.625rem #05e91fc5;
    border-radius: 1.25rem;
}

#name-button{
    z-index: 2;
    background-color: transparent;
}

/*CONFIGURAÇÔES ESPECÌFICAS NAVBAR2 */

#nav2 {
    display: none;
    align-items: center;
    justify-content: start;
    gap: 0.938rem;
    padding: 0.313rem;
    padding-left: 0.938rem;
}
.fa-bars {
    cursor: pointer;
    padding: 0.938rem 0.5rem;
    position: absolute;
    right: 5%;
}

.fa-bars:hover {
    border: 0.063rem solid white;
    border-radius: 0.563rem;
}

#collapseNavBar {
    flex-direction: column;
    background-color: #444;
    list-style: none;
}

#collapseNavBar a {
    text-decoration: none;
    color: #fff;
}

#collapseNavBar li {
    padding: 0.938rem;
}

.listItems {
    align-items: center;
    justify-content: center;
    flex-direction: column;
    margin: 0.313rem;
    background-color: #555;
    width: 100%;

}

.listItems a {
    padding: 0.438rem;
    width: 100%;
}
.listItems a:hover {
    background-color: #39B547;
    transition: 0.4s;
}

@media screen and (max-width: 53.125rem) {
    
    nav {
        width: 100%;
        border-radius: 0rem;
    }

}

@media screen and (max-width: 46.875rem) {
    
    #nav1 {
        display: none;
    }

    #nav2 {
        display: flex
    }

    #botaoAdd{
        width: 6.25rem;
    }

}

@media screen and (max-width: 12.5rem) {
    
    #nav1 {
        display: none;
    }

    #nav2 {
        display: none;
    }

    #img {
        width:3.75rem;
    }

}


</style>