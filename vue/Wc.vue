<template>
    <div>
        <h2>{{ name }}</h2>
        <span>{{ age }}</span>        
    </div>
</template>
<script>
export default {
    name:'Wc',
    data() {
        return {
            name: WC,
            age: 18
        }
    },
}
</script>
<style lang="en">
    h2{
        background-color: aqua;
    }
</style>