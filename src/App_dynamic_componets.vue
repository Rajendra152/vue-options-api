<template>
    <div>
        <button @click="activeTab = 'TabA'">Tab A</button>
        <button @click="activeTab = 'TabB'">Tab B</button>
        <button @click="activeTab = 'TabC'">Tab C</button>

        <keep-alive>
        <component :is="activeTab" />
        </keep-alive>
        
        <!-- <TabA v-if="activeTab === 'TabA'" />
        <TabB v-if="activeTab === 'TabB'" />
        <TabC v-if="activeTab === 'TabC'" /> -->

    </div>
</template>

<script>
    import TabA from './components/TabA.vue';
    import TabB from './components/TabB.vue';
    import TabC from './components/TabC.vue';
    export default {
        name: 'App',
        data(){
            return {

            }
        },
        components:{
            TabA,
            TabB,
            TabC,
        }
    }
</script>

<style scoped>

</style>