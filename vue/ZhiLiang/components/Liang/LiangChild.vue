<template>
    <div style="width: 392px;height: 230px;background-color: burlywood;">
        <div style="height: 46px;padding: 0px 10px;line-height: 46px;">
            <div style="border-bottom: solid 1px rgba(228, 206, 11, 0.623);">
                <span style="font-size: 20px;font-weight: bold;padding-left: 6px;border-left: solid 5px cornflowerblue;">{{items.title}}</span>
            </div>
        </div>
        <div style="display: flex;margin-top: 20px;">
            <div style="width: 150px;">
                <div style="margin: 0 auto;width: 120px;font-size:15px;text-align: center;">
                    <a href="#">
                        <img alt="1" class="a_img" :src="items.src" />
                        {{items.name}}
                    </a>
                </div>
            </div>
            <ul style="list-style: square;margin: 0 auto;width: 210px;">
                <li style="height: 25px;color: #3333336b;" v-for="item in items.li" :key="item.id">
                    <a :href="item.url" style="color: #2D8CF0;" v-text="item.name"></a>
                </li>
            </ul>
        </div>
    </div>
</template>
<script>
export default {
    props:{
        items:Object
    }

}
</script>
<style scoped>
a{
    text-decoration: none;
}
.a_img{
    width: 120px;
    height: 90px;
    margin: 0 auto;
}
</style>