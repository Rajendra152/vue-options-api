<template>
    <div>
        <button @click="getposts">Load Posts</button>
        {{errorMsg}}
        <div v-for="post in posts" :key='post.id'>
            <h3>{{post.id}}. {{post.title}}</h3>
            <p>{{post.body}}</p>
            <hr />
        </div>
    </div>
</template>

<script>
    import axios from "axios";
    export default {
        name:'PostList',
        // added created() method to load data on page load
        // created(){
        //     this.getposts()
        // },
        data(){
            return {
                posts:[],
                errorMsg:'',
            }
        },
        methods:{
            getposts(){
                axios.get('https://jsonplaceholder.typicode.com/posts/')
                .then((response) =>{
                    console.log(response.data);
                    this.posts=response.data;
                })
                .catch((error) =>{
                    console.log(error);
                    this.errorMsg='Error retrieving posts';
                })
            }
        }
    }
</script>

<style scoped>

</style>