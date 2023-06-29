<template>
    <div v-if="posts.length" class="my-post-list">
        <post-item 
            v-for="post in posts"
            :post="post" 
            :key="post.id"
            @remove="$emit('remove', post)"
             />
    </div>
    <h2 class="text" v-else>
        Tere are no posts, add a post!
    </h2>
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
        width: 50%;
        margin: auto;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-top: 30px;
    }

    .text {
        text-align: center;
        color: red;
    }

</style>