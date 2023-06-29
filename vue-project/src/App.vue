<template>
        <div>
            <div class="head">
                <div class="head-content">
                    <div>
                        <my-button @click="openDialog">Open dialog</my-button>
                    </div>
                    
                    <my-select :options="sortOptions" v-model="selectedSort" />
                </div>
            </div>
            <my-dialog v-model:show="dialogIsOpen">
                <post-form @create="createPost" />

            </my-dialog>
            <post-list :posts="posts" @remove="removePost" />
            

        </div>
</template>

<script>
import PostForm from './components/PostForm.vue';
import PostList from './components/PostList.vue';
import axios from 'axios'
export default {
    components: {
        PostForm,
        PostList
    },
    data() {
        return {
            posts: [],
            dialogIsOpen: false,
            selectedSort: '',
            sortOptions: [
                {value: 'title', name: 'By Title'},
                {value: 'name', name: 'By Name'}
            ]

        }
    },
    methods: {
        createPost(post) {
            this.posts.push(post);
            this.dialogIsOpen = false;
        },
        removePost(post) {
            this.posts = this.posts.filter(p => p.id !== post.id)
        },
        openDialog() {
            this.dialogIsOpen = true;
        },
        async fetchPosts() {
            try {
                const {data} = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=5');
                this.posts = data
                console.log(this.posts)
            } catch (error) {
                alert(error)
            }
        },
        

    },
    mounted() {
            this.fetchPosts()
        }

}
</script>

<style>
    .head {
        padding-top: 20px;
        width: 100%;
        display: flex;
        justify-content: center;
    }

    .head-content {
        width: 50%;
        display: flex;
        justify-content: space-between;
    }

</style>