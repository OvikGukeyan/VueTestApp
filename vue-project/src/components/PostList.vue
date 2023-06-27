<template>
    <div class="my-post-list">
        <post-item 
            v-for="post in posts"
            :post="post" 
            :key="post.id"
            @remove="$emit('remove', post)"
             />
    </div>
</template>

<script>
    import PostItem from './PostItem.vue'
    export default {
        components: {PostItem},
        props: {
            posts: {
                type: Array,
                required: true,
            }
        }
    }
</script>

<style>
    .my-post-list {
        width: 40%;
        margin: 50px auto;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

</style>