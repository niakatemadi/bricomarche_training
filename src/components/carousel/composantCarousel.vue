<template>
  <div class="componentCarousel">
    <div class="carousel-inner">
      <carouselItem
        v-for="(slide, index) in slides"
        :key="`item-${index}`"
        :currentSlide="currentSlide"
        :index="index"
        :slide="slide"
      />
    </div>
  </div>
</template>

<script>
import carouselItem from './carouselItem.vue';

export default {
  name: 'composantCarousel',
  components: { carouselItem },
  data() {
    return {
      currentSlide: 0,
      intervalId: null,
    };
  },
  props: {
    slides: {
      type: Array,
      required: true,
    },
  },
  methods: {
    setCurrentSlide(index) {
      this.currentSlide = index;
    },
  },
  mounted() {
    this.intervalId = setInterval(() => {
      const index =
        this.currentSlide < this.slides.length - 1 ? this.currentSlide + 1 : 0;
      this.currentSlide = index;
    }, 2000);
  },
  beforeDestroy() {
    clearInterval(this.intervalId);
  },
};
</script>
<style scoped>
.componentCarousel {
  border: 1px solid blue;
  display: flex;
  justify-content: center;
}
.carousel-inner {
  border: 1px solid red;
  position: relative;
  width: 900px;
  height: 400px;
  overflow: hidden;
}
</style>
