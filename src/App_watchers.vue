<script>
export default {
    name: 'App',
    data(){
        return {
            volume: 0,
            movie: ' ',
            movieInfo: {
                title:'',
                actor: '',
            },
            movieList: ['Rajendra', 'Prasad'],
        }
    },
    methods:{
    },
    computed:{
    },
    watch: {
        volume: {
        handler(newValue, oldValue) {
            if (newValue > oldValue && newValue === 16) {
            alert(
                'Listening to a high volume for a long time may damage your hearing'
            )
            }
        },
        immediate: true,
        },
        movie: {
            handler(newValue){
            console.log(`Calling API with movie name = ${newValue}`);
            },
            immediate: true,
        },
        movieInfo: {
            handler(newValue){
                console.log(`Calling API with movie title = ${newValue.title} and actor = ${newValue.actor}`);
            },
            deep: true,
        },
        movieList: {
            handler(newValue){
                console.log(`New movie name ${newValue}`);
            },
            // deep: true, //no need of deep watching here as we are concating the array and displaying new array
        }
    }
}
</script>

<template>
    <h2>Volume Tracker (0-20)</h2>
    <h3>Current Volume - {{ volume }}</h3>
    <div>
        <button @click="volume += 2">Increase</button>
        <button @click="volume -= 2">Decrease</button>
    </div>
    <input type="text" v-model="movie" />
    <input type="text" v-model="movieInfo.title" />
    <input type="text" v-model="movieInfo.actor" />
    <div>
        <button @click="movieList = movieList.concat(['Wonder Woman'])">Add Movie</button>
    </div>
</template>

<style>

</style>