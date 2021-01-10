<template>
    <li class="list-group-item" @click= "selectedVideo">
        <img :src="getThumbnailUrl" />{{video.snippet.title}}
    </li>
</template>

<script>
export default {
    name:'VideoListItem',
    props: ['video'],
    computed: {
        getThumbnailUrl() {
            return this.video.snippet.thumbnails.default.url;
        }
    },
    methods: {
        selectedVideo: function() {
            this.$emit('SelectedVideo', this.video);
        }
    }
}
</script>

<style>
    li {
        display: flex;
        cursor: pointer;
    }
    li:hover {
        background-color: #eeeeee;
    }
</style>