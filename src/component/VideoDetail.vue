<template>
    <div>
        {{selectedVideo.snippet.title}}
    </div>
</template>

<script>
export default {
    name: 'VideoDetail',
    props: ['selectedVideo']
}
</script>