<template ref="list">
    <ul>
        <Item v-for="item in thing" :item="item" :key="item.id" />
    </ul>

</template>
<script>
import Item from './Item'
export default {
    name:"list",
    components:{
        Item
    },
    props:["thing"]
}
</script>
<style scoped>
ul{
    box-sizing: border-box;
    width: 35%;
    list-style: none;
    margin: 10px auto;
    padding: 0%;
    border: blue 1px solid;
}
</style>