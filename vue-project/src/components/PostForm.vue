<template>
    <form class="my-form" @submit.prevent>
        <my-input v-model="post.title" type="text" placeholder="title" />
        <my-input v-model="post.body" type="text" placeholder="body" />
        <my-button @click="createPost">Create</my-button>
    </form>
</template>

<script>

export default {
    data() {
        return {
            post: {
                title: "",
                body: "",
            }
        };
    },
    methods: {
        createPost() {
            this.post.id = Date.now();
                this.$emit("create", this.post);
            this.post = {
                title: "",
                body: "",
            };
        }
    },
}
</script>

<style>
.my-form {
    display: flex;
    flex-direction: column;
    width: 40%;
    margin: 30px auto;
}
</style>