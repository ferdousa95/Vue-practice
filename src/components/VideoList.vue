<template>
    <ul>
        <VideoListItem v-for="video in videos" v-bind:key="video"> 
            {{ video }}
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
    }
}
</script>

<style>

</style>