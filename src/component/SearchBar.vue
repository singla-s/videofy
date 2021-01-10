<template>
    <div>
        <input/>
        <button @click = "onInput" class="btn btn-primary">
            Search
        </button>
    </div>
</template>

<script>
export default {
    name: "SearchBar",
    methods: {
        onInput: function(event) {
            this.$emit('newSearch', event.target.value);
        }
    }
}
</script>

<style scoped>
input {
    width: 75%;
    margin-left: 10%;
}
button {
    margin: 0 10px;
    width: 100px;
    height: 35px;
    padding-bottom: 33px;
}
</style>