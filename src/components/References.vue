<template>
  <div class="carousel" @mouseover="stopAutoSlide" @mouseleave="startAutoSlide">
    <div class="carousel-container" :style="{ transform: `translateX(${-currentIndex * 100}%)` }">
      <div class="slide" v-for="(reference, index) in references" :key="index" :style="getSlideStyles(index)">
        <div :class="['reference-item', { 'large': index === currentIndex }]">
          <h3>{{ reference.title }}</h3>
          <p>{{ reference.content }}</p>
        </div>
      </div>
    </div>
    <button class="carousel-prev" @click="prevSlide">
      <img src="https://i.postimg.cc/t4sR51JH/Arrow-1.png" alt="">
    </button>
    <button class="carousel-next" @click="nextSlide">
      <img src="https://i.postimg.cc/BnRSwqPP/Arrow-2.png" alt="">
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      references: [
      { title: 'Reference 1', content: 'Content for Reference 1' },
        { title: 'Reference 2', content: 'Content for Reference 2' },
        { title: 'Reference 3', content: 'Content for Reference 3' },
        { title: 'Reference 4', content: 'Content for Reference 4' },
        { title: 'Reference 5', content: 'Content for Reference 5' },
        { title: 'Reference 6', content: 'Content for Reference 6' },
        { title: 'Reference 7', content: 'Content for Reference 7' },
        { title: 'Reference 8', content: 'Content for Reference 8' },
        { title: 'Reference 9', content: 'Content for Reference 9' },
        { title: 'Reference 10', content: 'Content for Reference 10' },
        { title: 'Reference 11', content: 'Content for Reference 11' },
      ],
      currentIndex: 0,
      intervalId: null
    };
  },
  methods: {
    prevSlide() {
      this.currentIndex = (this.currentIndex - 1 + this.references.length) % this.references.length;
    },
    nextSlide() {
      this.currentIndex = (this.currentIndex + 1) % this.references.length;
    },
    startAutoSlide() {
      this.intervalId = setInterval(this.nextSlide, 3000); 
    },
    stopAutoSlide() {
      clearInterval(this.intervalId);
    },
    getSlideStyles(index) {
      return { flex: `0 0 ${index === this.currentIndex ? 50 : 25}%` };
    }
  },
  mounted() {
    this.startAutoSlide();
  },
  beforeUnmount() {
    clearInterval(this.intervalId);
  }
};
</script>

<style scoped>
.carousel {
  position: relative;
  width: 100%;
  height: 50%;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

.carousel-container {
  display: flex;
  transition: transform 0.5s ease;
}

.slide {
  flex: 20%; 
  text-align: center;
}

.reference-item {
  padding: 20px;
  transition: transform 0.3s;
}

.reference-item.large {
  transform: scale(1); 
}

.carousel-prev,
.carousel-next {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(0, 0, 0, 0.5);
  color: white;
  padding: 10px;
  border: none;
  cursor: pointer;
  z-index: 1;
}

.carousel-prev {
  left: 10px;
}

.carousel-next {
  right: 10px;
}

.carousel-next {
  color: #1BF2B5;
}

.carousel-next:hover {
  color: #0FA66E;
}
</style>
