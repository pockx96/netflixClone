<template>
    <div id="SideNav" class="flex z-40 items-center w-[120px] h-screen bg-black relative">
        <img class="absolute top-0 w-[35px] mt-10 ml-10" src="/images/netflix-logo.png" alt="">
        <div>
            <div class="py-2 mx-10 my-6">
                <Magnify fillColor="#f2f2f2" :size="40" class="cursor-pointer" />
            </div>
            <div class="py-2 mx-10 my-6">
                <HomeOutline fillColor="#f2f2f2" :size="40" class="cursor-pointer" />
            </div>
            <div class="py-2 mx-10 my-6">
                <TrendingUp fillColor="#f2f2f2" :size="40" class="cursor-pointer" />
            </div>
            <div class="py-2 mx-10 my-6">
                <Television fillColor="#f2f2f2" :size="40" class="cursor-pointer" />
            </div>
            <div class="py-2 mx-10 my-6">
                <MovieOutline fillColor="#f2f2f2" :size="40" class="cursor-pointer" />
            </div>
            <div class="py-2 mx-10 my-6">
                <Plus fillColor="#f2f2f2" :size="40" class="cursor-pointer" />
            </div>
        </div>
    </div>
</template>

<script setup>
import Magnify from 'vue-material-design-icons/Magnify.vue';
import HomeOutline from 'vue-material-design-icons/HomeOutline.vue';
import TrendingUp from 'vue-material-design-icons/TrendingUp.vue';
import Television from 'vue-material-design-icons/Television.vue';
import MovieOutline from 'vue-material-design-icons/MovieOutline.vue';
import Plus from 'vue-material-design-icons/Plus.vue';

import ChevronLeft from 'vue-material-design-icons/ChevronLeft.vue';
</script>

<style></style>