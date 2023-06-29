<template>
    <div>
        <h2 @mouseover="incrementCount">Hovered {{ count }}</h2>
    </div>
</template>

<script>
    import CounterMixin from '../mixins/counter';
    export default {
        name:"HoverCounter",
        mixins:[CounterMixin],
    }
</script>

<style scoped>

</style>