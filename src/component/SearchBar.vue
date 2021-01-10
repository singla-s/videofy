<template>
    <div>
        <input @input = "changeSearchTerm"/>
        <button @click = "onInput" class="btn btn-primary">
            Search
        </button>
    </div>
</template>

<script>
export default {
    name: "SearchBar",
    data() {
        return { searchTerm: "" };
    },
    methods: {
        changeSearchTerm: function(event) {
            this.searchTerm = event.target.value;
        },
        onInput: function() {
            this.$emit('newSearch', this.searchTerm);
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