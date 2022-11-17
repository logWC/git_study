<template>
    <div>
        <input type="text" v-fco @keyup.enter="Add" />
    </div>
</template>
<script>
export default {
    name:"Add",
    methods:{
        // 添加li
        Add(event){
            if(event.target.value != ""){
            const thing_obj = {
                id:Date.now(),
                thing:event.target.value,
                check:true
            }
            this.$emit('add',thing_obj)
            event.target.value = ""
            }
        }
    },
    directives:{
        fco:{
            inserted(e){
                e.focus();
            }
        }
    }
}
</script>
<style scoped>
    input{
        box-sizing: border-box;
        display: block;
        width: 35%;
        margin: auto;
        padding: 5px;
    }
    input:focus{
        border: blueviolet 1px solid;
        color: brown;
        outline: none;
    }
</style>