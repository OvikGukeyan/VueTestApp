<template>
    <div>
        <div>
            <post-form @create="createPost"/>
            <post-list  
                :posts="posts"
                @remove="removePost"
                />


        </div>
        
    </div>
</template>

<script>
import PostForm from './components/PostForm.vue';
import PostList from './components/PostList.vue';

export default {
    components: {
        PostForm,
        PostList
    },
    data() {
        return {
            posts: [
                { id: 1, title: 'article', body: 'article body' },
                { id: 2, title: 'article 2', body: 'article body 2' },
                { id: 3, title: 'article 3', body: 'article body 3' },
            ],
           
        }
    },
    methods: {
        createPost(post) {
            this.posts.push(post)
        },
        removePost(post) {
            this.posts = this.posts.filter(p => p.id !== post.id)
        }

    }

}
</script>

<style></style>