<template>
  <div>
   <div class="stay-put-head">
      <h1 class="mb-1">References</h1>
      <p class="mb-4"></p>
      <hr>
    </div>
    <div class="row">
      <div class="carousel-index col-6 col-sm-6">
        <div class="current-index-content px-3">
          <h3>Current Index Content:</h3>
          <h6>{{ references[currentIndex].title }}</h6>
          <p>{{ references[currentIndex].content }}</p>
          <p>{{ references[currentIndex].person }}</p>
        </div>
        <button class="carousel-prev" @click.prevent="prevSlide">
          <img src="https://i.postimg.cc/t4sR51JH/Arrow-1.png" alt="">
        </button>
        <button class="carousel-next" @click.prevent="nextSlide">
          <img src="https://i.postimg.cc/BnRSwqPP/Arrow-2.png" alt="">
        </button>
      </div>

      <div class="carousel px-5 col-6 col-sm-6">
        <div class="carousel-container rotating-carousel px-5" :style="carouselContainerStyle">
          <div class="slide " v-for="(reference, index) in references" :key="index" :style="getSlideStyles(index)">
            <div class="reference-item px-3" :class="{ 'large': index === currentIndex }">
              <p>{{ reference.person }}</p>
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
  </div>
</template>

<script>
export default {
  props: ["mySkill"],
};
</script>

<style scoped>
.cardp {
  background-color: #0e8388;
}

.par {
  color: #2E4F4F;
}

img {
  background-color: #2E4F4F;
  height: 10rem;
  width: 100%;
}
</style>
