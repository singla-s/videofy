<template>
    <div class="container">
        <div>
            <h1>Videofy</h1>
            <SearchBar @newSearch = "onNewSearch"></SearchBar>
        </div>
        <div>
            <VideoDetail v-if="selectedVideo" :selectedVideo = "selectedVideo"></VideoDetail>
        </div>
        <div>
            <VideoList :videos = 'videos' @SelectedVideo = "selectedVideoEvent"></VideoList>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    import SearchBar from './component/SearchBar';
    import VideoList from './component/VideoList';
    import VideoDetail from './component/VideoDetail';

    const API_KEY = 'AIzaSyA4VVORodCybMMVHmCgDonF_FblN3Naq_A';

    export default{
        name: "App",
        components: {
            SearchBar,
            VideoList,
            VideoDetail
        },
        data: function(){
              return {
                  videos: [],
                  selectedVideo: null
                  };
            },
        methods: {
            onNewSearch(newTerm){
                let header = {
                    key: API_KEY,
                    type: 'video',
                    part: 'snippet',
                    q: newTerm 
                };
                axios.get('https://www.googleapis.com/youtube/v3/search',{params: header})
                .then((response) => {
                    this.videos = response.data.items;
                });
            },
            selectedVideoEvent(event) {
                this.selectedVideo = event;
            }
        }
    };
</script>

<style scoped>
h1 {
    text-align: center;
}
</style>