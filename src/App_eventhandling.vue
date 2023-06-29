<script>

export default {
    name: "App",
    data(){
        return {
            name: "Rajendra",
            count: 0,
        }
    },
    methods: {
        increment(num,event){
            this.count += num;
            console.log("Event",event);
        },
        decrement(num){
            this.count -= num;
        },
        reset(num){
            this.count = num;
        },
        ChangeName(){
            this.name = "Prasad";
        }
    }
}

</script>

<template>
    <div>
    <h2>{{ name }}</h2>

    <!-- we can replace v-on: directive with @ -->

    <!-- <button v-on:click="name='Prasad'">Change Name onclick</button>
    <button @mouseover="name='Prasad'">Change Name on mouseover</button> -->

    <button @click="ChangeName($event), increment(1,$event)">Change Name</button>

    <h2>{{count}}</h2>
    <button @click="increment(1, $event)">Increment</button>
    <button @click="decrement(1)">Decrement</button>
    <button @click="reset(0)">Reset</button>


    </div>
</template>

<style scoped>

</style>