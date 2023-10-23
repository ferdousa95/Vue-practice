<template>
    <li class="list-group-item" v-on:click="onVideoSelect">
        <img class="mr-3" v-bind:src="thumbnailUrl" />
        <div class = "media-body">
            {{ videoTitle }}
        </div>
    </li>
</template>

<script>
export default {
    name: 'VideoListItem',
    props: {
        video: String
    },
    computed: {
        thumbnailUrl() {
            return this.video.snippet.thumbnails.default.url;
        },
        videoTitle() {
            return this.video.snippet.title;
        }
    },
    methods: {
        onVideoSelect() {
            this.$emit('videoSelect', this.video);
        }
    }
}
</script>

<style scoped>
    li {
        display: flex;
        cursor: pointer;
    }
    li:hover {
        background-color: #eee;
    }
</style>