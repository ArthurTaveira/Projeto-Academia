<template>

        <!--DIV para telas pequenas-->
    <div class="container" id="pagPhotos">
      
        <button class="arrowLeft control" aria-label="Previous image">
            <i class="fa-solid fa-arrow-left fa-2xl" style="color: #020202;"></i>
        </button>

        <button class="arrowRight control" aria-label="Next Image">
            <i class="fa-solid fa-arrow-right fa-2xl" style="color: #020202;"></i>
        </button>
        
        <div class="galleryWrapeer">
            <div class="gallery">
            <img src="https://source.unsplash.com/random/250x250/?beach" alt="Beach Image" 
            class="item currentItem"> 
            <img src="https://source.unsplash.com/random/250x250/?animal" alt="Animal Image" class="item currentItem">
            <img src="https://source.unsplash.com/random/250x250/?street" alt="Street Image" class="item currentItem">
            <img src="https://source.unsplash.com/random/250x250/?zoo" alt="Zoo Image" class="item currentItem">
            <img src="https://source.unsplash.com/random/250x250/?model" alt="Model Image" class="item currentItem">
            </div>
        </div>
    </div>
</template>

<script >
export default {
    name: 'PagPhotosSmall',
    mounted() {
    const controls = document.querySelectorAll(".control");
    let currentItem = 0;

    console.log(controls)
    const items = document.querySelectorAll(".item");
    const maxItems = items.length;

    controls.forEach((control) => {
    control.addEventListener("click", (e) => {
        let isLeft = e.target.classList.contains("arrowLeft");

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

.container {
  position: relative;
  max-width: 33.75rem;
  margin: 0 auto;
  display: none;
  padding: 1.25rem 2.5rem;
}

.galleryWrapeer {
  overflow-x: auto;
}

.arrowLeft,
.arrowRight {
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


.arrowRight {
  right: 0;
  left: auto;
  text-align: right;
}

.gallery {
  display: flex;
  flex-flow: row nowrap;
  gap: 0.938rem;
}

.item {
  width: 15.625rem;
  height: 15.625rem;
  flex-shrink: 0;
  transition: all 600ms ease-in-out;
  opacity: 0.5;
}

.currentItem {
  opacity: 1;
}

/* This is from w3schools */
/* 
https://www.w3schools.com/howto/howto_css_hide_scrollbars.asp */
/* Hide scrollbar for Chrome, Safari and Opera */
.galleryWrapeer::-webkit-scrollbar {
  display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
.galleryWrapeer {
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}


@media screen and (max-width: 37.5rem){
    .container {
        display: block
    }
}
</style>