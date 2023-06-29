<script>
export default {
    name:'Raj',
    data(){
        return {
            baseMultiplier: 5,
            baseValue: 2,
        }
    },
    methods: {
        add(a,b,c){
            return a+b+c;
        },
        multiply(num){
           return num*this.baseMultiplier;
        },
    },
}

</script>

<template>
<div>
    <h2>{{2+30}}</h2>
    <h2>add method {{add(20,30,10)}}</h2>
    <h2>Multiply method {{multiply(5)}}</h2>
    <h2>Multiply method {{multiply(baseValue)}}</h2>
</div>
</template>

<style scoped>

</style>