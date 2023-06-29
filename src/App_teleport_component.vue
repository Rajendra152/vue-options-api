<template>
    <teleport to="#portal-app">
        <Portal />
    </teleport>
</template>

<script>
    import Portal from './components/Portal.vue';
    export default {
        name: 'App',
        data(){
            return{}
        },
        methods:{},
        computed:{},
        components:{
            Portal
        },
    }
</script>

<style scoped>

</style>