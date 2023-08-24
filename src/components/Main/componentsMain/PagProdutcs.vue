<template>
  <div class="title" >

    <h2>Compre nossos produtos!</h2>

    <div>
      <span id="span1">TopFitness</span>
        <span id="span2">produtos</span>
    </div>

</div>
     <div id="slider">
         <div class="wrapper">
          <i id="left" class="fa-solid fa-angle-left"></i>
          <ul class="carousel">
            <li class="card">
              <MiniCardProduct/>
            </li>

            <li class="card">
              <MiniCardProduct/>
            </li>

            <li class="card">
              <MiniCardProduct/>
            </li>

            <li class="card">
              <MiniCardProduct/>
            </li>

            <li class="card">
              <MiniCardProduct/>
            </li>

            <li class="card">
              
            <MiniCardProduct/>
          </li>

          </ul>
          <i id="right" class="fa-solid fa-angle-right"></i>
             </div>
     </div>
</template>

<script >
 import MiniCardProduct from './MiniCardProduct.vue'
    export default {
        name: 'PagProducts',
        data(){
            return {
                wrapper: '',
                carouser: '',
                firstCardWidth: '',
                arrowBtns: '',
                carouselChildrens: [],
                isDragging: '',
                isAutoPlay: '',
                cardPerView: '',
            }
        },
        components: {
          MiniCardProduct
        },
        mounted(){
            this.wrapper = document.querySelector(".wrapper");
            this.carousel = document.querySelector(".carousel");
            this.firstCardWidth = this.carousel.querySelector(".card").offsetWidth;
            this.arrowBtns = document.querySelectorAll(".wrapper i");
            this.carouselChildrens = [...this.carousel.children];

            this.isDragging = false, 
            this.isAutoPlay = true, this.startX, this.startScrollLeft, this.timeoutId;
            // Get the number of cards that can fit in the carousel at once
            this.cardPerView = Math.round(this.carousel.offsetWidth / this.firstCardWidth);
            // Insert copies of the last few cards to beginning of carousel for infinite scrolling
            this.carouselChildrens.slice(-this.cardPerView).reverse().forEach(card => {
                this.carousel.insertAdjacentHTML("afterbegin", card.outerHTML);
            });
            // Insert copies of the first few cards to end of carousel for infinite scrolling
            this.carouselChildrens.slice(0, this.cardPerView).forEach(card => {
                this.carousel.insertAdjacentHTML("beforeend", card.outerHTML);
            });
            // Scroll the carousel at appropriate postition to hide first few duplicate cards on Firefox
            this.carousel.classList.add("no-transition");
            this.carousel.scrollLeft = this.carousel.offsetWidth;
            this.carousel.classList.remove("no-transition");
            // Add event listeners for the arrow buttons to scroll the carousel left and right
            this.arrowBtns.forEach(btn => {
                btn.addEventListener("click", () => {
                    this.carousel.scrollLeft += btn.id == "left" ? -this.firstCardWidth : this.firstCardWidth;
                });
            });
            const dragStart = (e) => {
                this.isDragging = true;
                this.carousel.classList.add("dragging");
                // Records the initial cursor and scroll position of the carousel
                this.startX = e.pageX;
                this.startScrollLeft = this.carousel.scrollLeft;
            }
            const dragging = (e) => {
                if(!this.isDragging) return; // if isDragging is false return from here
                // Updates the scroll position of the carousel based on the cursor movement
                this.carousel.scrollLeft = this.startScrollLeft - (e.pageX - this.startX);
            }
            const dragStop = () => {
                this.isDragging = false;
                this.carousel.classList.remove("dragging");
            }
            const infiniteScroll = () => {
                // If the carousel is at the beginning, scroll to the end
                if(this.carousel.scrollLeft === 0) {
                    this.carousel.classList.add("no-transition");
                    this.carousel.scrollLeft = this.carousel.scrollWidth - (2 * this.carousel.offsetWidth);
                    this.carousel.classList.remove("no-transition");
                }
                // If the carousel is at the end, scroll to the beginning
                else if(Math.ceil(this.carousel.scrollLeft) === this.carousel.scrollWidth - this.carousel.offsetWidth) {
                    this.carousel.classList.add("no-transition");
                    this.carousel.scrollLeft = this.carousel.offsetWidth;
                    this.carousel.classList.remove("no-transition");
                }
                // Clear existing timeout & start autoplay if mouse is not hovering over carousel
                clearTimeout(this.timeoutId);
                if(!this.wrapper.matches(":hover")) autoPlay();
            }
            const autoPlay = () => {
                if(window.innerWidth < 800 || !this.isAutoPlay) return; // Return if window is smaller than 800 or isAutoPlay is false
                // Autoplay the carousel after every 2500 ms
                this.timeoutId = setTimeout(() => this.carousel.scrollLeft += this.firstCardWidth, 2500);
            }
            autoPlay();
            this.carousel.addEventListener("mousedown", dragStart);
            this.carousel.addEventListener("mousemove", dragging);
            document.addEventListener("mouseup", dragStop);
            this.carousel.addEventListener("scroll", infiniteScroll);
            this.wrapper.addEventListener("mouseenter", () => clearTimeout(this.timeoutId));
            this.wrapper.addEventListener("mouseleave", autoPlay);
                    }
                }


</script>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600&display=swap');

.title {
  margin-top: 3rem 0;
}

#slider {
  display: flex;
  align-items: center;
  justify-content: center;
}
.wrapper {
  max-width: 68.75rem;
  width: 100%;
  position: relative;
}
.wrapper i {
  top: 50%;
  height:3.125rem;
  width: 3.125rem;
  cursor: pointer;
  font-size: 1.25rem;
  position: absolute;
  text-align: center;
  line-height: 3.125rem;
  background: #fff;
  border-radius: 50%;
  box-shadow: 0 0.188rem 0.375rem rgba(0,0,0,0.23);
  transform: translateY(-50%);
  transition: transform 0.1s linear;
}
.wrapper i:active{
  transform: translateY(-50%) scale(0.85);
}
.wrapper i:first-child{
  left: -1.375rem;
}
.wrapper i:last-child{
  right: -1.375rem;
}
.wrapper .carousel{
  display: grid;
  grid-auto-flow: column;
  grid-auto-columns: calc((100% / 4) - 0.875rem);
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  gap: 2rem;
  border-radius: 0.5rem;
  scroll-behavior: smooth;
  scrollbar-width: none;
}
.carousel::-webkit-scrollbar {
  display: none;
}
.carousel.no-transition {
  scroll-behavior: auto;
}
.carousel.dragging {
  scroll-snap-type: none;
  scroll-behavior: auto;
}
.carousel.dragging .card {
  cursor: grab;
  user-select: none;
}
.carousel :where(.card, .img) {
  display: flex;
  justify-content: center;
  align-items: center;
}
.carousel .card {
  scroll-snap-align: start;
  height: 30.375rem;
  list-style: none;
  background: rgb(255, 255, 255);
  cursor: pointer;
  flex-direction: column;
  border-radius: 0.5rem;
  
}
.card .img img {
  width: 8.75rem;
  height: 8.75rem;
}
.carousel .card h2 {
  font-weight: 500;
  font-size: 1.56rem;
  margin: 1.875rem 0rem 0.313rem;
}
.carousel .card span {
  color: #6A6D78;
  font-size: 1.31rem;
}

@media screen and (max-width: 75rem) {
  .wrapper .carousel {
    grid-auto-columns: calc((100% / 3) - 0.563rem);
  }
}

@media screen and (max-width: 56.25rem) {
  .wrapper .carousel {
    grid-auto-columns: calc((100% / 2) - 0.563rem);
  }
}

@media screen and (max-width: 31.25rem) {
  .wrapper .carousel {
    grid-auto-columns: calc((100% /1) - 0.563rem)
   }
}

@media screen and (max-width: 37.5rem) {
  #slider, .title {
    display: none;
  }
}

</style>