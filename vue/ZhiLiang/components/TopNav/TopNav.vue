<template>
    <div class="vertex">
        <div class="nav">
            <a href="#" v-for="item in TopNavUrls" :key="item.id">{{ item.title }}</a>
        </div>
    </div>
</template>
<script>
export default {
    name:"TopNav",
    props:['TopNavUrls']
}
</script>
<style scoped>
.vertex{
    min-width: 1200px;
    background-color: white;
}
.nav{
    display: flex;
    width: 1200px;
    height: 50px;
    line-height: 50px;
    margin: 0 auto;
}
.nav a{
    width: 150px;
    font-weight: bold;
    color: rgb(2, 24, 24);
    text-align: center;
}
.nav a:hover{border-bottom: rgb(255, 187, 0) solid 5px;}
</style>