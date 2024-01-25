<template>
    <div>
        <img src="" alt="Product Image">
        <span>{{ title }} </span>
        <span>{{ price }} </span>
    </div>
</template>


<script>
import Product from '@/Shop/Orders.vue';

export default {
    props: {
        title: String,
        price: Number,
    }
}
</script>
