<template>
    <input class="my-input" :value="modelValue"  @input="updateInput" type="text">
</template>

<script>
    export default {
        name: 'my-input',
        props: {
            modelValue: [String, Number]
        },
        methods: {
            updateInput(event) {
                this.$emit('update:modelValue', event.target.value)
            }
        }
    }
</script>

<style>
    .my-input {
        height: 50px;
        border-radius: 8px;
        padding-left: 15px;
        margin-bottom: 30px;
    }
</style>