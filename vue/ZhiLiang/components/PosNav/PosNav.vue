<template>
<div class="vertex">
    <span>职位导航</span>
    <div>
        <ul>
            <li v-for="(items,index) in PosNavLi"  :key="index">
                <span 
                :class="{'yellowgreen':index == num}" 
                @click="div_block(index)">{{ items.title }}
                </span>
                <div :class="{'block':index == num}">{{ items.title }}
                    <button @click="div_block(-1)">×</button>
                </div>
            </li>
        </ul>
    </div>
</div>
</template>
<script>
export default {
    name:"PosNav",
    props:['PosNavLi'],
    data() {
        return {
            num:-1
        }
    },
    methods:{
        div_block(index){
            this.num = index
        },
    }
}
</script>
<style scoped>
.vertex{
    width: 1200px;
    margin: 10px auto;
    background-color: rgb(92, 98, 185);
}
.vertex > span{
    box-sizing: border-box;
    width: 10%;
    display: inline-block;
    padding: 10px 0px 10px 50px;
    font-weight: bold;
}
.vertex > div{
    width: 90%;
    display: inline-flex;
    justify-content: center;
}
ul{
    box-sizing: border-box;
    list-style-type: none;
    display: flex;
    justify-content: center;
    position: relative;
}
ul li > span{
    padding: 3px 14px;
    user-select: none;
}
ul li div{
    width: 100%;
    position: absolute;
    top: 100%;
    left: 0%;
    background-color: yellowgreen;
    display: none;
}
.block{
    display: block;
}
.yellowgreen{
    background-color: yellowgreen;
}
</style>