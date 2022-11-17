<template>
    <div>
        <input type="checkbox" @change="change" :checked="yellow">
        <span>已完成任务{{item_ok}}/总任务{{items_ok}}</span>
        <button @click="items_clear">删除已选择</button>
    </div>
</template>
<script>
export default {
    props:["thing"],
    methods: {
        // 全选框点击触发
        change(e){
            this.$emit('foter_check',e.target.checked)
        },
        // 删除已选择的li
        items_clear(){
            this.$emit('App_items_clear')
        }
    },
    computed:{
        // 已完成任务数量
        item_ok(){
            return this.thing.reduce((pre,value) => value.check?pre+1:pre, 0)
        },
        // 总任务数量
        items_ok(){
            return this.thing.length
        },
        // 判断已完成与总任务是否相等
        yellow(){
            return this.item_ok==this.items_ok&&this.items_ok!=0?true:false
        }
    }
}
</script>
<style scoped>
div{
    box-sizing: border-box;
    width: 35%;
    font-size: 10px;
    background-color: burlywood;
    margin: auto;
    padding: 10px 0px;
}
</style>