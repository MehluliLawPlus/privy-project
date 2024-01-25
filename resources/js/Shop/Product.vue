<template>
    <div>
        <span>{{ title }} </span> 
        <img src="" alt="Product Image">
        <span>{{ price }} </span>
    </div>
</template>

<script>
export default {
    props: {
        title: String,
        price: Number,
    }
}
</script>
