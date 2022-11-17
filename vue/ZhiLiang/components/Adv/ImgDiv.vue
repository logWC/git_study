<template>
    <div class="ImgDiv">
        <a :href="b.url">
            <img :src="b.src" alt="1">
            <ul>
                <li
                v-for="(i,index) in new Array(4)" 
                @mouseenter="mouse(index)"
                @mouseleave="leave"
                :class="{'back': a == index}"
                :key="index"></li>
            </ul>
        </a>
    </div>
</template>
<script>
export default {
    name:"ImgDiv",
    props:['imgs'],
    data() {
        return {
            int:null,
            num: 0
        }
    },
    methods: {
        // 定时器触发事件
        img_mount() {
            if(this.num<this.imgs.length-1){
                this.num+=1
            }
            else{
                this.num=0
            }
        },
        // 鼠标穿入时
        mouse(index){
            this.num = index
            clearInterval(this.int)
        },
        // 鼠标穿出时
        leave(){
            this.int = setInterval(this.img_mount,2000)
        }
    },
    computed:{
        // 切换li样式
        a(){
            return this.imgs[this.num].id - 1
        },
        // 切换图片地址
        b(){
            return this.imgs[this.num]
        }
    },
    mounted(){
        // 启动定时器
        this.int = setInterval(this.img_mount,2000)
    },
}
</script>
<style scoped>
.ImgDiv{
    display: inline-block;
    width: 690px;
    height: 378px;
    margin-left: 10px;
    position: relative;
}
.ImgDiv ul{
    list-style-type: none;
}
.ImgDiv li{
    width: 14px;
    height: 14px;
    border: olive 1px solid;
    border-radius: 100%;
    position: absolute;
    top: 86%;
}
.ImgDiv ul li:nth-child(1){
    left: 45%;
}
.ImgDiv ul li:nth-child(2){
    left: 50%;
}
.ImgDiv ul li:nth-child(3){
    left: 55%;
}
.ImgDiv ul li:nth-child(4){
    left: 60%;
}
.ImgDiv img{
    width: 690px;
    height: 378px;
}
.back{
    background-color: orange;
}
</style>