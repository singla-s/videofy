<template>
    <ul class="list-group">
        <VideoListItem v-for="(video) of videos" :key="video.id.videoId" :video= "video" @SelectedVideo = "selectedVideo">
        </VideoListItem>
    </ul>
</template>

<script>
import VideoListItem from './VideoListItem';

export default {
    name: "VideoList",
    props: ['videos'],
    components: {
        VideoListItem
    },
    methods: {
        selectedVideo: function(event) {
            this.$emit('SelectedVideo', event);
        }
    }
}
</script>

<style>

</style>