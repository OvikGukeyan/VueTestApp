<template>
    <div class="my-item">
        <div>
            <div> that is {{ post.title }} and that is {{ post.body }}</div>
        </div>

        <div>
            <my-button @click="$emit('remove', post)" >Delete</my-button>
        </div>
    </div>
</template>

<script>

export default {
    props: {
        post: {
            type: Object,
            requred: true,
        }
    },
}
</script>

<style>
    .my-item {
        height: 70px;
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: space-around;
        border: 1px solid #000;
        border-radius: 8px;
        margin-bottom: 15px;
        padding: 5px;
    }

</style>