<template>
    <div>
        Tab C content
        <input type="text" v-modal="name" placeholder='name' />
    </div>
</template>

<script>
    export default {
        name: 'TabC',
        data(){
            return{
                name: '',
            }
        }
    }
</script>

<style scoped>

</style>