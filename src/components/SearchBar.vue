<template>
    <div>
        <input @input="onInput"/>
    </div>
</template>

<script>

export default({
    name: 'SearchBar',
    methods: {
        onInput: function(e) {
            this.$emit('termChange', e.target.value) //emitting event to the parent App component. $ is to prevent confusion if other variable with the same name exists
        }
    },
 
})
</script>

<style>

</style>
