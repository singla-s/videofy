<template>
    <div>
        <input @input = "onInput"/>
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
    display: block;
    width: 75%;
    margin: auto;
}
</style>