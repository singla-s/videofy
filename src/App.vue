<template>
    <div>
        <h1>Hello, World!</h1>
        <SearchBar @newSearch = "onNewSearch"></SearchBar>
    </div>
</template>

<script>
import axios from 'axios';
    import SearchBar from './component/SearchBar';
    const API_KEY = 'AIzaSyDQPsUczUrmUkBqdHLFWnorH-5LtgrOdg4';

    export default{
        name: "App",
        components: {SearchBar},
        methods: {
            onNewSearch: (newTerm) => {
                let header = {
                    key: API_KEY,
                    type: 'video',
                    part: 'snippet',
                    q: newTerm 
                };
                axios.get('https://www.googleapis.com/youtube/v3/search',{params: header}).then((response) => {
                    console.log(response);
                });
            }
        }
    };
</script>