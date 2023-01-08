<script setup>
import { ref } from 'vue'
const colores = 'red'
</script>

<script>
import navBar from './components/navBar.vue'
import carousel from './components/carousel.vue'

export default {
    components: {
        navBar,
        carousel
    },
    data() {
        return {
            bannerBackground: '',
            color: 'red',
            MovieName: 'Fantastic Beasts: The Secrets of Dumbledore',
            Overview: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Autem odio, quos ex mollitia earum ipsa ad distinctio vel dolore soluta rerum cumque, saepe laudantium in. Cumque tempore quaerat laboriosam natus!',
            vote_average: 0
        }
    },
    mounted() {
        console.log(this.color)
        document.getElementById('app').style.backgroundImage = "";
        document.getElementById('app').style.backgroundSize = "100vw, 40vh";
        document.getElementById('app').style.backgroundRepeat = "no-repeat";
    },
    methods: {
        changeSelectedMovie(movie) {
            console.log(movie)
            document.getElementById('app').style.backgroundImage = `url('https://image.tmdb.org/t/p/original${movie.backdrop_path}')`;
            this.MovieName = movie.title || movie.name
            this.Overview = movie.overview
            this.vote_average = Math.round(movie.vote_average * 10)
            // backdrop_path
        },
        pulse(obj){

            if(obj == 'prev') this.$refs.CAROUSEL.prev()
            else this.$refs.CAROUSEL.next()

            document.getElementById(obj).classList.add('ping')
            document.getElementById(obj + '2').classList.add('ping2')

            setTimeout(()=>{
                document.getElementById(obj).classList.remove('ping')
                document.getElementById(obj + 2).classList.remove('ping2')
            }, 1000)
            return
        }
    },

};
</script>

<template>
    <div class="flex">
        <navBar style="z-index:20" />
        <div class="w-[97vw] h-full ">

            <div id="content" class="overflow-y-auto  flex flex-col pt-[4em] 2xl:pt-[8em] gap-8 2xl:gap-20 pl-[6vw]">
                <div class="flex flex-col gap-4 max-w-[50vw] h-[12em]">
                    <span id="SelectedMovieName" class="text-4xl 2xl:text-6xl font-bold text-white drop-shadow-2xl">{{
                        MovieName
                    }}</span>
                    <div class="flex justify-between w-[8em] backdrop-blur-[2px]  py-2 px-4 rounded cursor-default	" style="background-color: rgba(107,114,128,.4)">
                        <img src="./assets/tmdb.svg" class="max-w-[2em]"/>
                        <span style="font-family: 'Space Grotesk', sans-serif;" class="text-white cursor-default	">{{ vote_average }} % </span>
                    </div>
                    <span id="SelectedMovieDescription"
                        class="text-md 2xl:text-lg max-w-[100%] shadow-inner-2xl text-white drop-shadow-2xl">{{ Overview }}</span>
                </div>
                <div class="flex justify-between items-center">
                    <div class="flex gap-4">
                        <button class="bg-primary px-12 py-2 rounded-lg">
                            <span class="font-bold text-white ">Watch Now</span>
                        </button>
                        <button class="border py-2 px-4 rounded-lg backdrop-blur-sm font-bold text-white"> + </button>
                    </div>
                    <div class="gap-4 pr-8 flex">
                        <div class="flex h-7 w-7 relative">
                            <span id='prev' class=" absolute inline-flex h-full w-full rounded-full bg-[#1C98CB] opacity-75"></span>
                            <span id='prev2' class="hover:scale-[1.1] duration-300 pingfather relative inline-flex rounded-full h-7 w-7 bg-[#1C98CB]"  @click="pulse('prev')">
                                <img class="p-1 rotate-180" src="./assets/noun-arrow-1920815.svg"/>
                            </span>
                        </div>
                        <div class="flex h-7 w-7 relative">
                            <span id='next' class=" absolute inline-flex h-full w-full rounded-full bg-[#1C98CB] opacity-75"></span>
                            <span id='next2' class="hover:scale-[1.1] duration-300  pingfather relative inline-flex rounded-full h-7 w-7 bg-[#1C98CB]"  @click="pulse('next')">
                                <img class="p-1 " src="./assets/noun-arrow-1920815.svg"/>
                            </span>
                        </div>
                    </div>
                </div>
                <div>
                    <carousel ref="CAROUSEL" :type="'trending'" @changeSelectedMovie="changeSelectedMovie" />
                    <div class="h-[100vh]">
                        
                    </div>
                </div>


            </div>


        </div>
    </div>
</template>

<style >
#app {
    display: flex;
    background-color: v-bind(colores);
}

body {
    font-family: 'DM Sans', sans-serif;
    background-color: black !important;
    z-index: 0;
}

#teste {
    background-color: v-bind(colores);
}

* {
    --background: v-bind(colores)
}

.ping {
    animation: ping 1s cubic-bezier(0, 0, 0.2, 1) forwards;
    @keyframes ping {

        75%,
        100% {
            transform: scale(2);
            opacity: 0;
        }
    }}

.ping2{
    transform: scale(1.2) !important;
    animation-duration: .5s !important;
}

.pingfather{
    cursor: pointer;
}



</style>
