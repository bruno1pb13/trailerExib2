<script >
import navBar from './components/navBar.vue'
import carousel from './components/carousel.vue'

export default {
    components: {
        navBar,
        carousel
    },
};
</script>

<template>
    <div class="flex">
        <navBar style="z-index:20"/>
        <div class="w-[97vw] h-full ">

            <div id="content" class="overflow-y-auto  flex flex-col pt-[4em] 2xl:pt-[8em] gap-8 2xl:gap-20 pl-[6vw]">
                <div class="flex flex-col gap-8 max-w-[50vw]">
                    <span id="SelectedMovieName" class="text-4xl 2xl:text-6xl font-bold">Fantastic Beasts: The Secrets
                        of
                        Dumbledore</span>
                    <span id="SelectedMovieDescription" class="text-xs 2xl:text-lg max-w-[100%]">Lorem ipsum dolor sit
                        amet
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
                        <button class="border rounded-xl px-2 mr-4" @click="$refs.CAROUSEL.prev()">{{ '<' }}</button>
                                <button class="border rounded-xl px-2" @click="$refs.CAROUSEL.next()">></button>
                    </div>
                </div>
                <div>
                    <carousel ref="CAROUSEL" />
                </div>
                
            </div>


        </div>
    </div>
</template>

<style>
#app {
    display: flex;
}

body {
    background-image: url("assets/bg.jpg");
    background-repeat: no-repeat;
    background-size: 100vw, 100vh;
    background-color: black;
    z-index: 0;
}
</style>
