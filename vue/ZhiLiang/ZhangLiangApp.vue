<template>
    <div>
        <!-- 头部搜索栏 -->
        <SouSuo />
        <!-- 头部导航 -->
        <TopNav :TopNavUrls="TopNavUrls" />
        <!-- 主体部分 -->
        <AdvApp />
        <!-- 职位导航 -->
        <PosNav :PosNavLi="PosNavLi" />
        <!-- 文章选择1 -->
        <LiangParent :choice_urls="'urls_1'" />
        <!-- 文章选择2 -->
        <LiangParent :choice_urls="'urls_2'" />
    </div>
</template>
<script>
import LiangParent from './components/Liang/LiangParent.vue'
import SouSuo from './components/Hear/HearApp.vue'
import TopNav from './components/TopNav/TopNav.vue'
import AdvApp from './components/Adv/AdvApp.vue'
import PosNav from './components/PosNav/PosNav.vue'
export default {
    name:"ZhangLiangApp",
    components: { LiangParent ,SouSuo, TopNav, AdvApp, PosNav},
    data(){
        return {
            TopNavUrls:
            [
                {id:'1',title:'首页',href:'#'},
                {id:'2',title:'城市频道',href:'#'},
                {id:'3',title:'政府单位招聘',href:'#'},
                {id:'4',title:'校园招聘',href:'#'},
                {id:'5',title:'高端职位',href:'#'},
                {id:'6',title:'海外招聘',href:'#'},
                {id:'7',title:'智联人才发展中心',href:'#'},
                {id:'8',title:'职Q社区',href:'#'}
            ],
            PosNavLi:
            [
                {title:"A"},
                {title:"B"},
                {title:"C"},
                {title:"D"},
                {title:"E"},
                {title:"F"},
                {title:"G"},
                {title:"H"},
                {title:"J"},
                {title:"K"},
                {title:"L"},
                {title:"M"},
                {title:"N"},
                {title:"P"},
                {title:"Q"},
                {title:"R"},
                {title:"S"},
                {title:"T"},
                {title:"V"},
                {title:"W"},
                {title:"X"},
                {title:"Y"},
                {title:"Z"}
            ]
        }
    }
}
</script>
<style>
ul{
    padding: 0%;
    margin: 0%;
}
body{
    margin: 0;
    padding: 0;
    background-color: whitesmoke;
}
a{
    text-decoration: none;
}
</style>