<script>
import Product from '@/Shop/Product.vue';
export default {
    components: {
        'product': Product,
    },
    methods:{
        // updateCatalog: function(product){
        //     this.console('received event');
        //     this.console(product);
        // }
        updateCatalog: function(){
            this.console('received event');
        }
    }

}
</script>

<template>
    <div>
       <!-- <div v-on:sendProduct="updateCatalog($event)"></div>
       <product v-on:sendProduct="updateCatalog($event)"/> -->
       <product v-on:sendProduct="updateCatalog"/>
    </div>
</template>


