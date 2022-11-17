<template>
    <li>
        <label>
            <input type="checkbox" :checked="item.check" @change="item_check(item.id,$event)" name="item.thing" />
            <span v-cloak>{{ item.thing }}</span>
        </label>
        <button @click="clear_list(item.id)">删除</button>
    </li>
</template>
<script>
export default {
    name:"Item",
    props:["item"],
    methods: {
        // $bus为事件总线的中间件
        item_check(d,event){
            // 改变li中的input
            this.$bus.$emit('App_item_check',d,event.target.checked)
        },
        clear_list(d){
            // 删除单个li
            this.$bus.$emit('App_delect_list',d)
        }
    },
}
</script>
<style scoped>
label{
    display: inline-block;
    width: 100%;
}
li{
    position: relative;
    padding: 5px 0;
}
li:hover{
    border: olive 1px solid;
}
li:hover > button{display: inline-block;}
button{
    display: none;
    position: absolute;
    right: 10px;
}
</style>