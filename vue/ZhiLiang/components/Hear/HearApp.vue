<template>
<div class="vertex">
    <div>
            <img src="@/assets/img/zlzp.png" alt="智联招聘" />
            <input type='text' placeholder='搜索公司职位、公司' />
            <button></button>
    </div>
</div>
</template>
<script>
export default {
    name:"Search"
}
</script>
<style scoped>
.vertex{
    min-width: 1200px;
    position: sticky;
    top: 0px;
    z-index: 1;
    background-color: white;
}
.vertex > div{
    width: 1200px;
    margin: 0 auto;
    box-sizing: border-box;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
}
button{
    width: 100px;
    height: 50px;
    background: url("../../../../assets/img/sousuo.png") no-repeat center;
    background-color: yellow;
    border: 1px solid rgba(0, 0, 0, 0.5);
}
input{
    box-sizing: border-box;
    outline: none;
    width: 700px;
    height: 50px;
    margin-left: 50px;
    padding-left: 10px;
    padding-right: 10px;
}
</style>