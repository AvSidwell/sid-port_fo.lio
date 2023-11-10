<template>
  <div class="stay-put-head">
    <h1 class="mb-1">References</h1>
    <p class="mb-4"></p>
    <hr />
  </div>
  <div class="row">
    <div class="carousel-index col-6 col-sm-6">
      <div class="current-index-content px-3">
        <h3>Current Index Content:</h3>
        <h6>{{ myTestimonials[currentIndex].name }}</h6>
        <p>{{ myTestimonials[currentIndex].view }}</p>
        <p>{{ myTestimonials[currentIndex].status }}</p>
      </div>
      <button class="carousel-prev" @click.prevent="prevSlide">
        <img src="https://i.postimg.cc/t4sR51JH/Arrow-1.png" alt="" />
      </button>
      <button class="carousel-next" @click.prevent="nextSlide">
        <img src="https://i.postimg.cc/BnRSwqPP/Arrow-2.png" alt="" />
      </button>
    </div>

    <div class="carousel px-5 col-6 col-sm-6">
      <div class="carousel-container rotating-carousel px-5" :style="carouselContainerStyle">
        <div class="slide " v-for="(testimonial, index) in myTestimonials" :key="index" :style="getSlideStyles(index)">
          <div class="reference-item px-3" :class="{ 'large': index === currentIndex }">
            <p>{{ testimonial.person }}</p>
          </div>
        </div>
      </div>
    </div>

    <div class="d-flex">
      <h1 class="m-1">The</h1>
      <h1 class="m-1">One</h1>
      <h1 class="m-1">Of</h1>
      <h1 class="m-1">The</h1>
      <h1 class="m-1">Best</h1>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentIndex: 0,
      intervalId: null
    };
  },
  methods: {
    prevSlide() {
      this.currentIndex = (this.currentIndex - 1 + this.carouselTestimonials.length) % this.carouselTestimonials.length;
    },
    nextSlide() {
      this.currentIndex = (this.currentIndex + 1) % this.carouselTestimonials.length;
    },
    getSlideStyles(index) {
      return { flex: `0 0 ${index === this.currentIndex ? 25 : 25}%` };
    },
  },
  computed: {
    carouselTestimonials() {
      return this.$store.state.myTestimonials;
    },
  },
};
</script>

<style scoped>
h1 {
  color: #D90754;
}

hr {
  margin: auto;
  margin-bottom: 1.5rem;
  width: 85%;
  color: #1BF2B5;
}
.large,
.current-index-content h3 {
  color: red;
  /* transition: form 0.5s ease; */
  /* font-size: 1.8em; */
  margin: 0;
}

.carousel {
  position: relative;
  height: 70vh;
  overflow: hidden;
  display: flex;
  align-items: center;
}

.carousel-index {
  height: 70vh;
}

.carousel-container {
  display: grid;
  align-items: center;
  align-content: center;
  grid-template-columns: auto auto auto;
  transition: transform 0.5s ease;
}

.slide {
  flex: 20%;
  text-align: center;
}

.carousel-prev,
.carousel-next {
  /* position: absolute; */
  /* top: 50%; */
  transform: translateY(-50%);
  background: rgba(0, 0, 0, 0.5);
  color: white;
  padding: 10px;
  border: none;
  cursor: pointer;
  z-index: 1;
}
button {
  margin-top: 50%;
  margin-left: 10%;
}
.carousel-prev {
  bottom: 1rem;
  left: 1rem;
}

.carousel-next {
  left: 10px;
}

.carousel-next {
  color: #1BF2B5;
}

.carousel-next:hover {
  color: #0FA66E;
}</style>
