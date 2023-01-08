<template>


<div class="w-[4vw] h-[100vh] py-4 flex flex-col justify-between items-center backdrop-blur-[4px] fixed" style="background-color: rgba(0, 0, 0, 0.5)">
            <div class="flex flex-col items-center gap-3">
                <a href="/" class="p-0 m-0 ">
                    <img class="cursor-pointer max-w-2 h-10 p-0 m-0 hover:scale-[1.2] duration-300"
                        src="../assets/YouTube-Icon-White-Logo.wine.svg" />
                </a>
            </div>
            <div class="flex flex-col items-center gap-4">

                <button class="hover:scale-[1.2] duration-300" data-tooltip-target="tooltip-search" data-tooltip-placement="right">
                    <img class="max-w-2 h-10 p-0 m-0" style="filter:invert()"
                        src="../assets/noun-search-5403228.svg" />
                        <div id="tooltip-search" role="tooltip"
                        class="absolute z-10 invisible inline-block px-3 py-2 text-sm font-medium text-white bg-gray-900 rounded-lg shadow-sm opacity-0 tooltip dark:bg-gray-700">
                        Search
                        <div class="tooltip-arrow" data-popper-arrow></div>
                    </div>
                </button>
                <a class="cursor-pointer hover:scale-[1.2] duration-300">
                    <img class="max-w-2 h-10 p-0 m-0" style="filter:invert()" src="../assets/noun-movie-5392777.svg"
                        alt="Tv Shows" data-tooltip-target="tooltip-movies" data-tooltip-placement="right" />
                    <div id="tooltip-movies" role="tooltip"
                        class="absolute z-10 invisible inline-block px-3 py-2 text-sm font-medium text-white bg-gray-900 rounded-lg shadow-sm opacity-0 tooltip dark:bg-gray-700">
                        Movies
                        <div class="tooltip-arrow" data-popper-arrow></div>
                    </div>
                </a>
                <a class="cursor-pointer hover:scale-[1.2] duration-300">
                    <img class="max-w-2 h-10 p-0 m-0" style="filter:invert()"
                        src="../assets/noun-clapperboard-1008444.svg" alt="Tv Shows" data-tooltip-target="tooltip-tv" data-tooltip-placement="right" />
                    <div id="tooltip-tv" role="tooltip"
                        class="absolute z-10 min-w-[5vw] invisible inline-block px-3 py-2 text-sm font-medium text-white bg-gray-900 rounded-lg shadow-sm opacity-0 tooltip dark:bg-gray-700">
                        Tv Shows
                        <div class="tooltip-arrow" data-popper-arrow></div>
                    </div>
                </a>
                <a class="cursor-pointer hover:scale-[1.2] duration-300">
                    <img class="max-w-2 h-10 p-0 m-0" style="filter:invert()" src="../assets/noun-japan-4903572.svg"
                        alt="Tv Shows"  data-tooltip-target="tooltip-anime" data-tooltip-placement="right"/>
                    <div id="tooltip-anime" role="tooltip"
                        class="absolute z-10 invisible inline-block px-3 py-2 text-sm font-medium text-white bg-gray-900 rounded-lg shadow-sm opacity-0 tooltip dark:bg-gray-700">
                        Animes
                        <div class="tooltip-arrow" data-popper-arrow></div>
                    </div>
                </a>
            </div>
            <div>asdas</div>
        </div>

    <!-- DISABLED TOP BAR -->

    <!-- <div class="w-[100%] ml-[4vw]	">
        <div class="py-4 flex justify-between w-[90%]">
            <div id="left" class="flex items-center">
                <a href="/" class="p-0 m-0">
                    <img class="cursor-pointer max-w-2 h-10 p-0 m-0"  src="../assets/YouTube-Icon-White-Logo.wine.svg"/>
                </a>
            </div>
            <div id="center" class="flex items-center">
                <div class="px-4">Movies</div>
                <div class="px-4">Tv shows</div>
                <div class="px-4">Series</div>
                <div class="px-4">Animations</div>
            </div>
            <div id="right" class="flex items-center">
                <span>Informações do perfil</span>
            </div>
        </div>
    </div> -->


</template>
