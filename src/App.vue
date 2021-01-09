<template>
    <div>
        <h1>Hello, World!</h1>
        <SearchBar></SearchBar>
    </div>
</template>

<script>
    import SearchBar from './component/SearchBar';

    export default{
        name: "App",
        components: {SearchBar} 
    };
</script>