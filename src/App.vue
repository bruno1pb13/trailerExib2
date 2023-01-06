<script >
import navBar from './components/navBar.vue'
import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import { ref } from 'vue'



export default {
    components: {
        navBar,
        Carousel,
        Slide,
        Pagination,
        Navigation,
    },
    methods:{
        prev(){
            this.$refs.teste.prev()
        
        },
        next(){
            this.$refs.teste.next()
        }
    }
};
</script>

<template>
    <div class="flex w-full">
        <div class="w-[4em] h-[100vh] py-4 pl-2 mr-12 flex flex-col justify-between items-center">
            <div>asdas</div>
            <div>asdas</div>
            <div>asdas</div>
        </div>
        <div class="w-full h-full">
            <navBar />
            <div id="content" class="overflow-y-auto h-[91vh] flex flex-col pt-[8em] gap-4">
                <div class="flex flex-col gap-4 max-w-[50vw]">
                    <span id="SelectedMovieName" class="text-4xl font-bold">Fantastic Beasts: The Secrets of
                        Dumbledore</span>
                    <span id="SelectedMovieDescription" class="text-xs max-w-[70%]">Lorem ipsum dolor sit amet
                        consectetur adipisicing elit. Autem odio, quos ex mollitia earum ipsa ad distinctio vel dolore
                        soluta rerum cumque, saepe laudantium in. Cumque tempore quaerat laboriosam natus!</span>
                </div>
                <div class="flex justify-between items-center">
                    <div class="flex gap-4">
                        <button class="bg-primary px-12 py-2 rounded-lg">
                            <span class="font-bold text-white ">Watch Now</span>
                        </button>
                        <button class="border py-2 px-4 rounded-lg backdrop-blur-sm font-bold text-white"> + </button>
                    </div>
                    <div class="gap-4 pr-8">
                        <button class="border rounded-xl px-2 mr-4" @click="prev">{{ '<' }}</button>
                                <button class="border rounded-xl px-2" @click="next">></button>
                    </div>
                </div>
                <div class="max-w-[77em]">
                    <div>
                        <carousel ref="teste" :items-to-show="5.5" :wrapAround="true">
                            <slide v-for="slide in 10" :key="slide" class="">
                                <div class="bg-[red] w-[11em] h-[12em] rounded">
                                    {{ slide }}
                                </div>
                            </slide>
    
                            <!-- <template #addons>
                                <navigation :id="'back'"/>
                                <pagination />
                            </template> -->
                        </carousel>
                    </div>
                </div>
            </div>


        </div>
    </div>
</template>

<style>
body {
    width: 100vw;
}

#app {
    width: 100vw;
    display: flex;
    background-image: url("assets/bg.jpg");
    background-repeat: no-repeat;
    background-size: cover;

}
.carousel__item {
  min-height: 200px;
  width: 100%;
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
