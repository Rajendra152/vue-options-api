<template>
    <div>
        <h4>App component text</h4>
        <ChildStyles />
    </div>
</template>

<script>
    import ChildStyles from './components/ChildStyles.vue';
    export default {
        name: 'App',
        components:{
            ChildStyles,
        },
        data(){
            return{

            }
        },
    }
</script>

<style scoped>
h4{
    color: orange;
}
</style>