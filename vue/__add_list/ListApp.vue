<template>
    <div>
        <HeaderAdd @add="add" />
        <List :thing="thing"  />
        <Foter :thing="thing" ref="foter" />
    </div>
</template>
<script>
import HeaderAdd from './header_add.vue'
import Foter from './foter.vue'
import List from './list.vue'
export default {
    name:"ListApp",
    components:{
        HeaderAdd,
        List,
        Foter
    },
    data() {
        return {
            thing:[
                {id:"1", thing:"喝水", check:true},
                {id:"2", thing:"吃饭不咯", check:false},
                {id:"3", thing:"抽烟不咯", check:false},
                {id:"4", thing:"喝酒不咯", check:false}
            ]
        }
    },
    methods: {
        add(e){
            // add：添加li
            this.thing.unshift(e)
        },
        App_delect_list(d){
            // item：删除单个li
            this.thing = this.thing.filter(value => value.id != d)
        },
        App_item_check(d,chec){
            // item：li中的多选框点击
            this.thing.forEach(val => {val.check = val.id==d?chec:val.check})
        },
        foter_check(chec){
            // foter：全选框点击
            this.thing.forEach(val => val.check = chec)
        },
        App_items_clear(){
            // 删除已选择的li
            this.thing = this.thing.filter(value => !value.check)
        }
    },
    mounted() {
        // 传给item的自定义事件
        // 用了全局总线
        // 适用于任何俩个组件
        this.$bus.$on('App_item_check',this.App_item_check)
        this.$bus.$on('App_delect_list',this.App_delect_list)
        // 传给foter的自定义事件
        // 用了ref绑定组件
        // 适用于 子传父数据
        this.$refs.foter.$on('foter_check',this.foter_check)
        this.$refs.foter.$on('App_items_clear',this.App_items_clear)
    }    
}
</script>
