<template>
    <div>
        <h2>{{ name }}</h2>
        <span>{{ age }}</span>        
    </div>
</template>
<script>
export default {
    name:'Jk',
    data() {
        return {
            name: JK,
            age: 17
        }
    },
}
</script>
<style lang="en">
    h2{
        background-color: aqua;
    }
</style>