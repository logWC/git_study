<template>
    <div class="vertex">
        <div class="NavUlImg">
            <ul class="ul_nav">
                <li><div>互联网IT</div><div>我是互联网</div></li>
                <li><div>金融</div><div>我是金融</div></li>
                <li><div>房地产/建筑</div><div>我是房地产</div></li>
                <li><div>贸易/零售/物流</div><div>我是贸易</div></li>
                <li><div>教育/传媒/广告</div><div>我是教育</div></li>
                <li><div>服务业</div><div>我是服务业</div></li>
                <li><div>市场/销售</div><div>我是市场</div></li>
                <li><div>人事/财务/行政</div><div>我是人事</div></li>
                <li><a href="#">全部职类</a></li>
            </ul>
            <ImgDiv :imgs="ImgDivImgs" />
        </div>
        <div class="ConponentCut">
            <div @click="tru=!tru">点击转换组件</div>
            <a href="#">我要招人 ></a>
            <DenLuA v-if="tru" />
            <DenLuB v-else />
        </div>
    </div>
</template>
<script>
// 登录组件
import DenLuA from './DenLuA.vue'
import DenLuB from './DenLuB.vue'
// 轮播组件
import ImgDiv from './ImgDiv.vue'
export default {
    name:"AdvApp",
    components: { DenLuA, DenLuB, ImgDiv },
    data() {
        return {
            tru: true,
            ImgDivImgs:[
                {id:'1',url:"https://wclili.vip",src:require("@/assets/img/大屏1.jpg")},
                {id:'2',url:"https://wclili.vip",src:require("@/assets/img/大屏2.jpg")},
                {id:'3',url:"https://wclili.vip",src:require("@/assets/img/大屏3.jpg")},
                {id:'4',url:"https://wclili.vip",src:require("@/assets/img/大屏4.jpg")}
            ],
        }
    }
}
</script>
<style scoped>
ul{
    list-style-type: none;
    padding: 0;
}
a{
    color: #000000;
}
.vertex{
    display: flex;
    width: 1200px;
    margin: 10px auto;
    height: 378px;
}
.NavUlImg{
    display: flex;
    align-items: center;
    width: 925px;
}
.ul_nav{
    display: inline-block;
    position: relative;
    width: 220px;
}
.ul_nav li{
    box-sizing: border-box;
}
.ul_nav li div:nth-child(1),.ul_nav li:last-child > a{
    display: block;
    box-sizing: border-box;
    width: 220px;
    height: 42px;
    line-height: 42px;
    background-color: white;
    padding-left: 24px;
}
.ul_nav li > div:nth-child(2){
    display: none;
    width: 700px;
    height: 378px;
    background-color: lightcoral;
    position: absolute;
    left: 220px;
    top: 0px;
}
.ul_nav li:hover > div:nth-child(2){
    display: block;
    z-index: 2;
}
.ul_nav li:hover > div:nth-child(1),.ul_nav li:hover > a{
    border-top: solid 1px rgb(0, 255, 200);
    border-bottom: solid 1px rgb(0, 204, 255);
    color: rgb(21, 82, 216);
}
.ConponentCut{
    width: 262px;
    height: 378px;
    background-color: coral;
    position: relative;
    box-sizing: border-box;
}
.ConponentCut > div:nth-child(1){
    display: inline-block;
    width: 52px;
    height: 52px;
    background-color: yellow;
    margin: 10px 0 0 10px;
}
.ConponentCut > div:nth-child(1) + a{
    width: 70px;
    font-size: 13px;
    position: absolute;
    top: 10px;
    right: 10px;
}
</style>