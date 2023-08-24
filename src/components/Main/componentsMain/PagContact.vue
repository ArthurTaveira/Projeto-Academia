<template>

    <div id="pagContact">
        <div id="contentText">

            <form>
            
            <label for="nome" class="labelForm">Nome:</label>
            <input type="text" name="" id="nome" class="inputControl
            " placeholder="Ex: Kerlon">

            <label for="celular" class="labelForm">Tel:</label>
            <input type="text" name="" id="celular" class="inputControl
            " placeholder="Ex: (88) 9 9974-12345">

            <label for="email" class="labelForm">Email:</label>
            <input type="email" name="" id="email" class="inputControl
            " placeholder="topfitness@email.com">

            <label for="msg" class="labelForm">Mensagem:</label>
            <textarea name="" id="msg" cols="40" rows="5" class="inputControl
            " >Sua Mensagem aqui!
            </textarea>
            <div id="botaoAdd"><span id="nameButton">Enviar</span></div>
        </form>
        </div>

        <div>
            <div id="contentTxtImg">
                <div class="title">

<h2>Entre em Contato!</h2>

<div>
  <span id="span1">TopFitness</span>
    <span id="span2">contato</span>
</div>
</div>
                <p id="paragrafo">Tire dúvidas com um de nossos tutores!</p>
            </div>
            <img src="/img/logo/imgCompleta2.0.png" alt="">
        </div>
    </div>
</template>

<script>
    export default {
        name: 'PagContact'
    }
</script>

<style scoped>

    .title{
        margin: 2rem;
        height: auto;
    }
       
 #pagContact{
        display:flex;
        flex-flow: row wrap;
        justify-content: space-evenly;
        align-items: center;
        gap: 0.625rem;
        width: 100%;
        margin-bottom: 1.875rem;
    }

    #contentText{
        position: relative;
        display: flex;
        flex-direction: column;
        justify-content: start;
        gap: 0.625rem;

    }

    form{
        background-color: #39B547;
        padding: 1.25rem;
        border-radius: 0.625rem;
        color:#fff;
    }

    #paragrafo {
        font-style: italic;
        font-size: 1.4rem;
        margin-bottom: 1rem;
    }

    #title {
        font-size: 1.8rem;
    }

    img{
        width: 31.25rem;
    }

    #contentTxtImg{
        display: flex;
        flex-direction: column;
        gap: 0.625rem;
        align-items: center;
        justify-content: center;
        margin: 1rem;

    }

    /* form */

    #botaoAdd{
        background-color: #222;
        color:azure;
        border-radius: 21.25rem;
        padding: 0.625rem 0.875rem;
        font-weight: bold;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 12.5rem;
        position: relative;
        margin: 0 auto;
        margin-top: 0.625rem;
    }

    #botaoAdd::before {
    content: "";
    border-radius: 1.25rem;
    background-color: #fff;
    position: absolute;
    display: block;
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

}

#botaoAdd:hover{
    color: rgb(57, 181, 71);
    transition: 0.3s;
    border-radius: 1.25rem;
    box-shadow: 0rem 0rem 0.75rem rgba(0, 0, 0, 0.637);
}

#nameButton{
    z-index: 2;
    background-color: transparent;
}

form {
        display: flex;
        flex-direction: column;
        gap: 0.2rem;
    }

    label{
        font-size: 1.1rem;
        font-weight: bold;
    }

    input, textarea
    {
        text-decoration: none;
        border: 0.1rem solid #222;
        padding: 1.2rem;
        margin-bottom: 0.5rem;
        border-radius: 1rem;
        font-size: 1rem;
    }

    @media screen and (max-width: 53.75rem) {
        #pagContact {
            flex-flow: column-reverse nowrap;
            align-items: center;
            justify-content: center;
        }

        #contentText {
            width: 85%;
        }

        #title {
            font-size: 2.5rem;
        }

        #paragrafo {
            font-size: 1.9rem;
        }
        img {
           display: none;
        }

        input, textarea {
            font-size: 1.2rem;
        }

    }

    @media screen and (max-width: 26.25rem) {
        #paragrafo {
            font-size: 1.5rem;
        }

        #contentText {
            width: 95%;
        }


        #contentTxtImg{
            margin: 1rem;
        }

        .iconeGrande {
            display: none;
        }

        #botaoAdd {
            font-size: 1.3rem;
        }

        input, textarea
         { 
        font-size: 1.2rem;
        }
    }

</style>
    
