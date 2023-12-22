<template>
    <video 
    :src="'/videos/'+movie.name+'.mp4'"
    autoplay
    loop
    muted
    class="absolute z-0 h-[600px] right-0 top-0"
    ></video>
    
</template>

<script setup>
    defineProps({movie:Object})
</script>
