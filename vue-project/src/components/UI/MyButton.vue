<template>
    <button class="my-button"> <slot></slot></button>
</template>


<script>
    export default {
        name: 'my-button'
    }
</script>


<style>
    .my-button {
        height: 40px;
        width: 150px;
        margin: auto;
        background-color: #fff;;
        border-radius: 8px;
        cursor: pointer;
    }

    .my-button:hover {
        background-color: darkgray;
    }

</style>