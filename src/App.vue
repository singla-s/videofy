<template>
    <div class="container">
        <div>
            <h1>Videofy</h1>
            <SearchBar @newSearch = "onNewSearch"></SearchBar>
        </div>
        <div>
            <VideoList :videos = 'videos'></VideoList>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    import SearchBar from './component/SearchBar';
    import VideoList from './component/VideoList';
    const API_KEY = 'AIzaSyDQPsUczUrmUkBqdHLFWnorH-5LtgrOdg4';

    export default{
        name: "App",
        components: {
            SearchBar,
            VideoList
        },
        data: function(){
              return {
                  videos: []
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
                    console.log(this.videos)
                });
            }
        }
    };
</script>

<style scoped>
h1 {
    text-align: center;
}
</style>