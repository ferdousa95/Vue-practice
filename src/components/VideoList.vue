<template>
    <ul class="list-group col-md-4" >
        <VideoListItem 
            v-for="video in videos" :key="video"
            v-bind:video="video"
            v-on:videoSelect="onVideoSelect"
        > 
            
        </VideoListItem>
    </ul>
</template>

<script>
import VideoListItem from './VideoListItem.vue';

export default {
    name: 'VideoList',
    props: {
        videos: Array
    },
    components: {
    VideoListItem,
    },
    methods: {
        onVideoSelect(video) {
            this.$emit("videoSelect", video);
        }
    }
}
</script>

<style>

</style>