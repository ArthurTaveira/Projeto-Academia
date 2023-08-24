<template>
    <div id="card">
        <img id='iconImg' :src="card.img" alt="">
        <h2 id="title">{{ card.titulo }}</h2>
        <p id="text"> {{ card.texto }}</p>
    </div>
</template>

<script>
    export default{
        name:'MiniCard',
        props: {
            card: Object
        }
    }

</script>

<style scoped>
    #card{
        width: 15.625rem;
        height: 15.625rem;
        border: black 0.063rem solid;
        border-radius: 0.438;
        margin: 0.625rem;
        position: relative;


        padding: 0.938rem;
        display: flex;
        flex-direction: column;
        justify-content: start;
        align-content: center;


        overflow: hidden;
        border-radius: 0.438rem;

        
    }
    #iconImg {
        width: 4.063rem;
        margin: 0rem 0.625rem;
    }
    #title{
        margin-top: 1.25rem;
    }
    #text{
        margin-top: 0.75rem;
    }

    #card::before {
    content: "";
background-color: #39B547;
    position: absolute;
    display: block;
    color: #fff;
    inset: 0;
    z-index: -1;
    transition: transform 400ms ease;
    transform-origin: 100%;
    transform: scaleX(0);
    
}

#card:hover::before {
    transform: scaleX(1);
    transition-duration: 500ms;
    transform-origin: 0%;
    border-radius: 0.438rem;
    color: white;
}

#card:hover{
    color: #fff;
    transition: 0.3s;
    box-shadow: 0rem 0rem 0.75rem rgba(0, 0, 0, 0.658);
}

@media screen and (max-width: 200px) {
    
    #card {
        width: 100%;
        margin: 10px;
        height: auto;
        pointer-events: none;
        justify-content: center;
        align-items: center;
    }


}

</style>