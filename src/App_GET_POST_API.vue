<template>
    <div>
    <CreatePost />
    <PostList />
    </div>
</template>

<script>
    import PostList from './components/PostList.vue';
    import CreatePost from './components/CreatePost.vue';
    export default {
        name: 'App',
        data(){
            return {

            }
        },
        components:{
            PostList,
            CreatePost,
        }
    }
</script>

<style scoped>

</style>