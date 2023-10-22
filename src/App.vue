<template>
    <div>
        <SearchBar v-on:termChange="onTermChange"></SearchBar>
        <VideoList v-bind:videos = "videos"> </VideoList>
    </div>
    
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar.vue';
import VideoList from './components/VideoList.vue';
const API_KEY = 'AIzaSyC2WEP3DhCfdjKQr9u--cl1ixvnzZKfZm0';

export default {
    name: 'App',
    components: {
    SearchBar,
    VideoList,
    },
    data() {
        return {
            videos: []
        };
    },
    methods: {
        onTermChange(searchTerm) {
            axios.get('https://www.googleapis.com/youtube/v3/search', {
                params: {
                    key: API_KEY,
                    type: 'video',
                    part: 'snippet',
                    q: searchTerm
                }
            }).then(response => {
                this.videos = response.data.items
            });
        }
    }
}
</script>