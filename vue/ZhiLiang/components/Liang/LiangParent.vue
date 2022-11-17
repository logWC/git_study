<template>
    <div class="di">
        <LiangChild v-for="lian in url" :items="lian" :key="lian.id" />
    </div>
</template>
<script>
import LiangChild from './LiangChild.vue'
export default {
    components: { LiangChild },
    props:["choice_urls"],
    data(){
        return {
            urls:{
            "urls_1":
            [
                {
                    id:"1",
                    title:"职场聚焦",
                    src:require("@/assets/img/zcjj.jpg"),
                    name:"不得不防的三类人",
                    li:[
                        {name:"如何从团建看公司好坏",url:"#",id:1},
                        {name:"内部转岗请谨慎！",url:"#",id:2},
                        {name:"别错把平台当本事",url:"#",id:3},
                        {name:"如何给自己增值？",url:"#",id:4},
                        {name:"这三种情况，预示该转型了",url:"#",id:5}
                    ]
                },
                {
                    id:"2",
                    title:"应届生求职",
                    src:require("@/assets/img/yjsqz.jpg"),
                    name:"应届生求职实录",
                    li:[
                        {name:'五种最常见的 "职场PUA"',url:"#",id:1},
                        {name:"灵活就业为什么会火？",url:"#",id:2},
                        {name:"晒加班是什么心理？",url:"#",id:3},
                        {name:"规避这3个副业误区",url:"#",id:4},
                        {name:"别把同事当朋友",url:"#",id:5}
                    ]
                },
                {
                    id:"3",
                    title:"社区精华",
                    src:require("@/assets/img/sqjh.jpg"),
                    name:"恋爱职业速配",
                    li:[
                        {name:"职场人减肥日志",url:"#",id:1},
                        {name:"9种职场超能力",url:"#",id:2},
                        {name:"职场人9大读书真相",url:"#",id:3},
                        {name:"老铁等级测试表",url:"#",id:4},
                        {name:"职场人自愈图鉴",url:"#",id:5}
                    ]
                }
            ],
            "urls_2":
            [
                {
                    id:"1",
                    title:"简历制作|模板",
                    src:require("@/assets/img/jlzz.jpg"),
                    name:"精美简历模板",
                    li:[
                        {name:"公司裁员的三个信号",url:"#",id:1},
                        {name:"3个加班潜规则",url:"#",id:2},
                        {name:"情绪控制有多重要",url:"#",id:3},
                        {name:"成功的人从不晒目标",url:"#",id:4},
                        {name:"听话，是职场最大的谎言",url:"#",id:5}
                    ]
                },
                {
                    id:"2",
                    title:"面试技巧",
                    src:require("@/assets/img/msjq.jpg"),
                    name:"工作群生存守则",
                    li:[
                        {name:'跨部门沟通指南',url:"#",id:1},
                        {name:"公司好不好，请假见分晓",url:"#",id:2},
                        {name:"职场正在淘汰这些人",url:"#",id:3},
                        {name:"频繁跳槽有多可怕？",url:"#",id:4},
                        {name:"怎样向领导汇报工作？",url:"#",id:5}
                    ]
                },
                {
                    id:"3",
                    title:"智联调研",
                    src:require("@/assets/img/zldy.jpg"),
                    name:"警惕 “职场PUA”",
                    li:[
                        {name:"如何谈加薪？",url:"#",id:1},
                        {name:"35岁还有上坡路吗？",url:"#",id:2},
                        {name:"哪些原因影响内部晋升？",url:"#",id:3},
                        {name:"为什么你不敢休假？",url:"#",id:4},
                        {name:"该考虑转行了！",url:"#",id:5}
                    ]
                }
            ],
            }
        }
    },
    computed:{
        url(){
            // 复用此组件
            return this.urls[this.choice_urls]
        }
    }
}
</script>
<style scoped>
.di{
    display: flex;
    justify-content: space-between;
    width: 1200px;
    margin: 10px auto;
}
</style>