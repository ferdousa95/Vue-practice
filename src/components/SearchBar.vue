<template>
    <div>
        <input v-on:input="onInput"/>
    </div>
</template>

<script>
export default {
    name: 'SearchBar',
    methods: {
        onInput: function(event) {
            this.$emit('termChange', event.target.value) // name of the event that changed. 
        }
    }
};
</script>

<style>

</style>