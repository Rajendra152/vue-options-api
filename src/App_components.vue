<script>
import Greet from './components/Greet.vue';
import Article from './components/Article.vue';
export default{
    name: "App",
    data(){
        return {
            firstname: "Sai",
            lastname: "kumar",
        }
    },
    components:{
        Greet,
        Article,
    }
}
</script>

<template>
    <div>
    <Greet name="Raj" hero-name="Ramcharan" />
    <Greet name="prasad" hero-name="NTR" />
    <Greet name="ashok" hero-name="Mahesh babu" />
    <Greet :firstname="name" :hero-name="lastname" />
    <Article id='my-article' title="article title" :likes="50" :isPublished="true"/>
    </div>

</template>

<style>

</style>