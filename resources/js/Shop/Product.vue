<template>
    <div class="product">
        <span>{{ title }} </span> 
        <img v-bind:src=url  alt="Product Image">
        <span>${{ price }} </span> <br>
        <a href="" @click="add()" class="right-button">+</a>
        <a href="" @click="sub()" class="left-button">-</a>
        <b>{{ quantity }}</b>
    </div>
</template>

<script>
export default {
    data(){
        return{
            quantity: 0,
        }
    },
    props: {
        title: String,
        price: String,
        url: String,
    },
    methods: {
        add: function(){
            this.quantity++;
            this.emit('sendProduct');
        },
        sub: function(){
            this.quantity--;
            this.emit('sendProduct', this.title, this.price, this.url);
        },
        sendProduct: function(){
            this.emit('sendProduct', this.title, this.price, this.url);
        },
    }
}
</script>

<style>
.product{
    width: 40%;
    padding: 2px 2px 2px 2px; 
    border-style: solid;
    border-width: 1px;
    border-color: black;
    img{
        background-color: blue;
    }
    .right-button{
        background-color: #04AA6D; /* Green */
        border: none;
        color: white;
        padding: 5px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        margin: 4px 2px;
        cursor: pointer;
        border-radius: 10px;
    }
    .left-button{
        background-color: #04AA6D; /* Green */
        border: none;
        color: white;
        padding: 5px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        margin: 4px 2px;
        cursor: pointer;
        border-radius: 10px;
    }
}
</style>