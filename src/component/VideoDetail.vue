<template>
    <div class="detail">
        <div>
            <iframe class="iframe" :src="videoUrl"></iframe>
        </div>
        <div>
            <h4>{{selectedVideo.snippet.title}}</h4>
        </div>
        <p>{{selectedVideo.snippet.description}}</p>
    </div>
</template>

<script>
export default {
    name: 'VideoDetail',
    props: ['selectedVideo'],
    computed: {
        videoUrl: function() {
            return `https://www.youtube.com/embed/${this.selectedVideo.id.videoId}`;
        }
    }
}
</script>

<style scoped>
.detail {
    padding: 2% 5%;
    border: 1px solid #ddd;
    border-radius: 4px;
}
.iframe {
    width: 100%;
    height: 500px;
}
</style>