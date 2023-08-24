<template>

<div class="title">

<h2>Compre nossos produtos!</h2>

<div>
  <span id="span1">TopFitness</span>
    <span id="span2">produtos</span>
</div>
</div>
    <!--DIV para telas pequenas-->
<div id="slider">

    <button class="arrow-left control" aria-label="Previous image">
        <i class="fa-solid fa-arrow-left fa-2xl" style="color: #020202;"></i>
    </button>

    <button class="arrow-right control" aria-label="Next Image">
        <i class="fa-solid fa-arrow-right fa-2xl" style="color: #020202;"></i>
    </button>

    <div class="galleryWrapper">
        
        <div class="gallery">
            <MiniCardProduct class="item currentItem"/>
            <MiniCardProduct class="item currentItem"/>
            <MiniCardProduct class="item currentItem"/>
            <MiniCardProduct class="item currentItem"/>
            <MiniCardProduct class="item currentItem"/>
            <MiniCardProduct class="item currentItem"/>
            
        </div>
    </div>
    
</div>
</template>

<script >
import MiniCardProduct from './MiniCardProduct.vue'
export default {

name: 'PagProductsSmall',
components: {
    MiniCardProduct
},
mounted() {
const controls = document.querySelectorAll(".control");
let currentItem = 0;

console.log(controls)
const items = document.querySelectorAll(".item");
const maxItems = items.length;

controls.forEach((control) => {
control.addEventListener("click", (e) => {
    let isLeft = e.target.classList.contains("arrow-left");

    if (isLeft) {
    currentItem -= 1;
    } else {
    currentItem += 1;
    }

    if (currentItem >= maxItems) {
    currentItem = 0;
    }

    if (currentItem < 0) {
    currentItem = maxItems - 1;
    }

    items.forEach((item) => item.classList.remove("currentItem"));

    items[currentItem].scrollIntoView({
    behavior: "smooth",
    inline: "center"
    });

    items[currentItem].classList.add("currentItem");
});
});
}
}

</script>

<style scoped>

.title {
    margin-top: 1.875rem;
    display: none;
}
#slider {
position: relative;
max-width: 33.75rem;
margin: 0 auto;
display: none;
padding: 1.25rem 2.5rem;
}

.galleryWrapper {
overflow-x: auto;
}

.arrow-left,
.arrow-right {
position: absolute;
top: 0;
left: 0;
right: auto;
bottom: 0;
font-size: 1.25rem;
line-height: 15.625rem;
width: 2.5rem;
transition: all 600ms ease-in-out;
cursor: pointer;
border: none;
background-color: transparent;
margin: 0 1.25rem;
}

.arrow-right {
right: 0;
left: auto;
text-align: right;
}

.gallery {
display: flex;
flex-flow: row nowrap;
flex-direction: row;

}

.item {
margin: 0.5rem;
flex-shrink: 0;
transition: all 600ms ease-in-out;
opacity: 0.5;
}

.currentItem {
opacity: 1;
}
.galleryWrapper::-webkit-scrollbar {
display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
.galleryWrapper {
-ms-overflow-style: none; /* IE and Edge */
scrollbar-width: none; /* Firefox */
}


@media screen and (max-width: 37.5rem){
#slider  {
    display: block
}

.title {
    display: flex;
}

}
</style>