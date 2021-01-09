<template>
    <div>
        <h1>Hello, World!</h1>
        <SearchBar @newSearch = "onNewSearch"></SearchBar>
    </div>
</template>

<script>
    import SearchBar from './component/SearchBar';
    const api_key = 'AIzaSyDQPsUczUrmUkBqdHLFWnorH-5LtgrOdg4';

    export default{
        name: "App",
        components: {SearchBar},
        methods: {
            onNewSearch: (newTerm) => {
                console.log(newTerm);
            }
        }
    };
</script>