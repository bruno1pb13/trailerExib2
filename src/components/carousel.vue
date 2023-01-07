<template>

  <carousel ref="teste" :items-to-show="itensToShow" :wrapAround="true">
    <slide v-for="slide in 10" :key="slide">
      <div class="bg-[red] w-[100%] h-[12em] rounded">
        {{ slide }}
      </div>
    </slide>
  </carousel>

</template>

<style scoped>
.carousel__item {
  background-color: var(--vc-clr-primary);
  color: var(--vc-clr-white);
  font-size: 20px;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.carousel__slide {
  padding: 10px;
}

.carousel__prev,
.carousel__next {
  box-sizing: content-box;
  border: 5px solid white;
}
</style>

<script>

import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import { ref } from 'vue'


export default {
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
    ref
  },

  data() {
    return {
      itensToShow : this.itensToShow()
    }
  },
  methods: {
    next() {
      this.$refs.teste.next()
    },
    prev() {
      this.$refs.teste.prev()
    },
    itensToShow(){
      console.log(screen.width)
      if(screen.width >= 1920) return 9

      if(screen.width >= 1366) return 6
      return 5
    }
  }
}

</script>