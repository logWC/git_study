<template>
    <div>
        <table border="1">
            <caption>Cart</caption>
            <tr>
                <th>Name</th>
                <th>Quantity</th>
                <th>(Standard) Price (USD)</th>
                <th>Sub-total-(USD)</th>
            </tr>
            <tr v-for="item in cartData" :key="item.id">
                <td> {{item.name}} </td>
                <td> {{item.qty}} </td>
                <td> {{item.price}} </td>
                <td>{{item.qty*item.price}}</td>
            </tr>
            <tr class="footer">
                <td colspan="3">Total</td>
                <td> {{USD}} </td>
            </tr>
        </table>
        <div class="div-button">
            <button @click="reset">Reset</button>
            <button>Checkout</button>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            cartData:
            [
                { id: 1, name: "Chicken Wing", category: "Food", qty: 3, price: 10 },
                { id: 2, name: "Pizza", category: "Food", qty: 1, price: 50 },
                { id: 3, name: "Hamburger", category: "Food", qty: 1, price: 12 },
                { id: 4, name: "Coca Cola", category: "Drink", qty: 2, price: 5 },
                { id: 5, name: "Orange Juice", category: "Drink", qty: 1, price: 15 },
                { id: 6, name: "Potato Chips", category: "Snack", qty: 1, price: 8 },
            ]
        }
    },
    methods: {
        reset(){
            this.cartData.forEach((val) => {
                val.qty = 0
            })
        }
    },
    computed:{
        USD(){
            var usd = 0;
            this.cartData.forEach((val) => {
                usd += val.qty*val.price
            })
            return usd
        }
    }
}
</script>
<style scoped>
table{
    width: 100%;
    border-collapse: collapse;
}
caption{
    text-align: left;
    font-weight: bold;
}
tr td:nth-child(1),tr th:nth-child(1){
    width: 150px;
    text-align: left;
}
tr td:nth-child(2),tr th:nth-child(2){
    text-align: center;
}
tr td:nth-child(3),tr th:nth-child(3){
    text-align: right;
}
tr td:nth-child(4),tr th:nth-child(4){
    text-align: right;
}
.footer td:nth-child(1),.footer td:nth-child(2){
    text-align: right;
}
.div-button{
    text-align: right;
}
.div-button button:nth-child(1){
    border: none;
    color: dodgerblue;
    background-color: inherit;
}
.div-button button:nth-child(2){
    border: none;
    color: aliceblue;
    background-color: dodgerblue;
    border-radius: 5px;
}
</style>