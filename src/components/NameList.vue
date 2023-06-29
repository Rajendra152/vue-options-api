<template>
    <div>
        <h3 v-for="name in names" :key='name.firstName'>
            <slot :firstName="name.firstName" :lastName="name.lastName"></slot>
        </h3>
    </div>
</template>

<script>
    export default {
        name:'NameList',
        data(){
            return{
                names: [
                    {
                        firstName: 'raj',
                        lastName: 'prasad',
                    },
                    {
                        firstName: 'praveen',
                        lastName: 'kasturi',
                    },
                    {
                        firstName: 'rajesh',
                        lastName: 'goli',
                    },
                ],
            }
        }
    }
</script>

<style scoped>

</style>