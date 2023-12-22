<template>
  <div class="fixed w-full h-screen ">
    <SideBar />
    <div class="fixed flex z-20 top-0 right-0 w-full h-1/2 bg-black pl-[120px] bg-clip-border">
      <div class="absolute z-30 h-[600px] left-[120px] w-3/4 right-0 top-0 bg-gradient-to-r from-black via-black" />
      <MovieDetails v-if="movie" :movie="movie"/>
      <div class="flex absolute self-end left-50 bottom-10 z-40 w-1/5 h-12 justify-between text-2xl font-bold">
        <button class="flex justify-evenly  rounded w-2/5 bg-white items-center cursor-pointer">
          <Play fillColor="#2c2c2c" :size="35" />
          Play
        </button>
        <button class="flex justify-evenly items-center rounded opacity-80  w-3/6 bg-slate-400 text-white cursor-pointer"> 
          <Info fillColor="#f2f2f2" :size="35" />More info</button>
      </div>
      <MainVideo v-if="movie" :movie="movie"/>
    </div>

    <div class="fixed z-30 bottom-0 right-0 w-full h-1/2 pl-[120px] overflow-auto ">
      <VideoCarousel category="Popular Movies" :movies="movies[0]"/>
      <VideoCarousel category="Horror Movies" :movies="movies[1]"/>
      <VideoCarousel category="Comedy Movies" :movies="movies[2]"/>
    </div>

    <div class="absolute z-20 h-4/6 left-[120px] w-full right-0 bottom-0 bg-gradient-to-t from-black via-black" />
  </div>

  <div v-if="showFullVideo">
      <div @click="showFullVideo = false" class="absolute z-50 p-2 m-4 bg-white bg-opacity-50 rounded-full cursor-pointer">
        <ChevronLeft fillColor="#FFFFFF" :size="40"/>
      </div>
      <video 
        :src="'/videos/'+movie.name+'.mp4'" 
        autoplay 
        loop
        controls
        class="absolute z-0 w-[100vw] h-full object-fit"
      />
    </div>
</template> 

<style></style>

<script setup>
import { onMounted, ref } from 'vue';
import movies from './movies.json'
import SideBar from './components/SideBar.vue';
import MainVideo from './components/MainVideo.vue';
import MovieDetails from './components/MovieDetails.vue';
import { useMovieStore } from './stores/movie'
import { storeToRefs } from 'pinia';
import VideoCarousel from './components/VideoCarousel.vue';
import ChevronLeft from 'vue-material-design-icons/ChevronLeft.vue';
import Play from 'vue-material-design-icons/Play.vue';
import Info from 'vue-material-design-icons/Information.vue';


const useMovie = useMovieStore()
const { movie, showFullVideo } = storeToRefs(useMovie)
const pathMovie = "/videos/"+movie.name+".mp4"

onMounted(() => {
  setTimeout(() => movie.value = movies[0][0], 100)
})
</script>
