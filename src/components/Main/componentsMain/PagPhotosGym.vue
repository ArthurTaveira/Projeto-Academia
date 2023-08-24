<template id='pagPhotos'>
    <div class="title">

        <h2>Galeria de Fotos</h2>
        <div>
            <span id="span1">TopFitness</span>
            <span id="span2">Fotos</span>
        </div>

    </div>
        
    <!--Div para telas grandes-->
    <div id="pagPhotos">
        
        <div class="setLine">
            
            <div class="Line">
                <atropos-component class="my-atropos">
                    <img src="/img/logo/imagemimagem.png" alt="">
                </atropos-component>

                <atropos-component class="my-atropos">
                    <img src="/img/logo/imagemimagem.png" alt="">
                </atropos-component>
                
            </div>
            
            <div class="Line">
                <atropos-component class="my-atropos">
                    <img src="/img/logo/imagemimagem.png" alt="">
                </atropos-component>

                <atropos-component class="my-atropos">
                    <img src="/img/logo/imagemimagem.png" alt="">
                </atropos-component>
            </div>

        </div>
        
        <div class="column">
            <atropos-component class="my-atropos">
                <img src="/img/logo/imagemimagem.png" alt="">
                </atropos-component>

            <atropos-component class="my-atropos">
                <img src="/img/logo/imagemimagem.png" alt="">
            </atropos-component>
        </div>

        
    </div>
    
</template>

<script>
    export default {
        name: 'PagPhotosGym'
    }
</script>

<style scoped>

/*Definindo o Gap e display Flex das Fotos */
    #pagPhotos, .Line, .column, .setLine {
        gap: 1.875rem;
        display: flex;
    }

    /* Definições Gerais da Pagina */
    #pagPhotos {
        flex-direction: row;
        align-items: center;
        justify-content: center;
        max-width: 100%;
        margin: 0.625rem;

    }
    
    /* Organização das Fotos */
    .Line {
        flex-flow: row;
    }
    .column {
        flex-direction: column;
    }
    .setLine {
        flex-direction: column;
    }
    img {
        cursor: pointer;
        width: 15.625rem;
    }
 
    @media screen and (max-width: 53.125rem) {
        #pagPhotos{
            flex-direction: column;
        }
        .column{
            flex-direction: row;
        }
    }

    @media screen and (max-width: 37.5rem) {
        #pagPhotos {
            display: none;
        }
    }

</style>