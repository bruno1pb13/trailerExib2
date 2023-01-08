<template>

  <carousel ref="teste" :items-to-show="itensToShow" :wrapAround="true">
    <slide v-for="content, index in data.results" :key="slide" @click="changeActive(index)">
      <div :style="'background:url(https://image.tmdb.org/t/p/w500/'+content.poster_path+')'" :class=" index == active ? 'active' : ''" style="background-size:cover" class="w-[100%] h-[12em] rounded">
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

.active{
  border: 5px solid white;
}


</style>

<script>

import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import { ref } from 'vue'
import axios from 'axios'

export default {
  props: ['type'],
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
    ref
  },

  data() {
    return {
      itensToShow : this.itensToShow(),
      data : [],
      active: 0
    }
  },
  mounted(){

    switch(this.type){
      case 'trending':
        this.getTrendingMovies()
        break
    }
  },
  methods: {
    next() {
      this.$refs.teste.next()
      if(this.active == this.data.results.length - 1) this.active = 0
      else this.active = this.active + 1
      this.changeActive(this.active)
    },
    prev() {
      this.$refs.teste.prev()
      if(this.active == 0) this.active = this.data.results.length - 1
      else this.active = this.active - 1
      this.changeActive(this.active)

    },
    itensToShow(){
      console.log(screen.width)
      if(screen.width >= 1920) return 9

      if(screen.width >= 1366) return 6
      return 5
    },
    async getTrendingMovies(){
      let options = {
        method: 'GET',
        url: defaultURL + '/tmdb/trending',
        headers: {
          'Content-Type': 'application/json'
        }
      }

      let response = await axios(options)
      if(response) this.data = response.data
      this.changeActive(0)
    },
    changeActive(id){

      this.active = id
      this.$emit('changeSelectedMovie', this.data.results[id])

    }
  }
}

</script>