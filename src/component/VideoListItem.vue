<template>
    <li class="list-group-item">
        <img :src="getThumbnailUrl" />{{video.snippet.title}}
    </li>
</template>

<script>
export default {
    name:'VideoListItem',
    props: ['video'],
    computed: {
        getThumbnailUrl() {
            return video.snippet.thumbnails.default.url;
        }
    }
}
</script>

<style>

</style>