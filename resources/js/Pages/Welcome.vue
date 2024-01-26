<script setup>
import { Head, Link } from '@inertiajs/vue3';
import Product from '../Shop/Product.vue';
import Catalog from '../Shop/Catalog.vue';

defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    },
    laravelVersion: {
        type: String,
        required: true,
    },
    phpVersion: {
        type: String,
        required: true,
    },
});

</script>

<template>
    <Head title="Basic-Login" />
    <div
        class="relative sm:flex sm:items-center min-h-screen bg-dots-darker bg-center bg-gray-100 dark:bg-dots-lighter dark:bg-gray-900 selection:bg-red-500 selection:text-white"
    >
        <div v-if="canLogin" class="sm:fixed sm:top-0 sm:right-0 p-6 text-end">
            <Link
                v-if="$page.props.auth.user"
                :href="route('dashboard')"
                class="font-semibold text-gray-600 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                >Dashboard</Link
            >

            <template v-else>
                <Link
                    :href="route('login')"
                    class="font-semibold text-gray-600 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                    >Log in</Link
                >
                <Link
                    v-if="canRegister"
                    :href="route('register')"
                    class="ms-4 font-semibold text-gray-600 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                    >Register</Link
                >
            </template>
        </div>

        <div class="product-listings">
            <b>MEALS</b>
            <!-- <product 
             title="Sadza and Stew" 
             price="1" 
             url="https://www.stockvault.net/data/2020/01/21/272703/preview16.jpg"
             />
            <product 
             title="Sadza and Zondo" 
             price="1" 
             url="https://www.stockvault.net/data/2007/03/01/96600/preview16.jpg"
             />
            <product
             title="Rice and Chicken" 
             price="2" 
             url="https://www.stockvault.net/data/2013/04/21/144292/preview16.jpg"
             />
            <product 
             title="Rice and Beans" 
             price="2" 
             url="https://www.stockvault.net/data/2020/06/14/276546/preview16.jpg"
             />
            <product 
             title="Pet"
             price="0.3" 
             url="https://www.stockvault.net/data/2007/03/01/98638/preview16.jpg"
             /> -->
            <product 
             title="Pepsi" 
             price="0.5" 
             url="https://media.istockphoto.com/id/1289738725/photo/plastic-bottle-of-coke-with-red-label-design-and-cap.jpg?s=1024x1024&w=is&k=20&c=SbGmMq4NXyKKWf_tARBqgKmD-StczotB8lKGZ0EXxCo="
             />
        </div>
        <div class="catalog">
            <b>Catalog</b>
            <catalog/>
        </div>
    </div>
</template>

<style>
.product-listings{
    width: 50%;
    padding-left: 10%;
    padding-top: 5%;
}
.bg-dots-darker {
    background-image: url("data:image/svg+xml,%3Csvg width='30' height='30' viewBox='0 0 30 30' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M1.22676 0C1.91374 0 2.45351 0.539773 2.45351 1.22676C2.45351 1.91374 1.91374 2.45351 1.22676 2.45351C0.539773 2.45351 0 1.91374 0 1.22676C0 0.539773 0.539773 0 1.22676 0Z' fill='rgba(0,0,0,0.07)'/%3E%3C/svg%3E");
}
@media (prefers-color-scheme: dark) {
    .dark\:bg-dots-lighter {
        background-image: url("data:image/svg+xml,%3Csvg width='30' height='30' viewBox='0 0 30 30' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M1.22676 0C1.91374 0 2.45351 0.539773 2.45351 1.22676C2.45351 1.91374 1.91374 2.45351 1.22676 2.45351C0.539773 2.45351 0 1.91374 0 1.22676C0 0.539773 0.539773 0 1.22676 0Z' fill='rgba(255,255,255,0.07)'/%3E%3C/svg%3E");
    }
}
</style>
