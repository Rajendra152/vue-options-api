<template>
    <div>
        <Card></Card>
        <Card>Card content</Card>
        <Card>
            <h2>Card content</h2>
        </Card>
        <Card>
            <img src='https://picsum.photos/200' />
        </Card>
        <Card>
            <template v-slot:header>
                <h3>Header</h3>
            </template>
            <template v-slot:default>
                <img src='https://picsum.photos/200' />
            </template>
            <template v-slot:footer>
                <button>View Details</button>
            </template>
        </Card>
        <NameList>
            <template v-slot:default='slotProps'>
                {{slotProps.firstName}} {{slotProps.lastName}}
            </template>
        </NameList>

        <NameList>
            <template v-slot:default='slotProps'>
                {{slotProps.firstName}}, {{slotProps.lastName}}
            </template>
        </NameList>

        <NameList>
            <template v-slot:default='slotProps'>
                {{slotProps.firstName}}
            </template>
        </NameList>

    </div>
</template>

<script>
import Card from './components/Card.vue';
import NameList from './components/NameList.vue';
    export default {
        name: 'App',
        components:{
            Card,
            NameList,
        }
    }
</script>

<style scoped>

</style>