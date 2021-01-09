<template>
    <ul class="list-group">
        <VideoListItem v-for="(video) of videos" :key="video.id.videoId" :video= "video">
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
    }
}
</script>

<style>

</style>