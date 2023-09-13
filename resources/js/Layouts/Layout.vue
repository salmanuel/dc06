<script setup>
    import MainNav from '@/Components/MainNav.vue'
    import { ref } from 'vue';
    import { Link } from '@inertiajs/vue3';

    let width = ref('w-[250px]')
    let hide = ref(false)

    function toggleWidth() {
        if(width.value == 'w-[250px]') {
            width.value = 'w-[100px]'
            hide.value = true
        }else {
            width.value = ['w-[250px]']
            hide.value = false
        }
    }
    // const isCollapsed = ref(false)

    // function toggleWidth() {
    //     isCollapsed.value = !isCollapsed.value;
    // }
</script>

<template>

<div class="flex min-h-screen">
    <div id="sidebar" class="bg-gray-900 p-6 duration-500" :class="width" style="position: relative;">
        <button class="text-xl text-gray-600" @click="toggleWidth" style="position: absolute; right: 10px; top:10px">
            <i class="fa-solid fa-bars"></i>
        </button>
        <div id="branding" :hidden="hide">
            <img src="https://icon-library.com/images/clients-icon-png/clients-icon-png-9.jpg" alt="Logo"
                class="w-[170px] h-[170px] mx-auto rounded-full object-cover">
            <h1 class="text-3xl text-center text-gray-200 my-6">Something</h1>

        </div>
        <hr class="border-gray-600" :hidden="hide">

        <!-- <div class="main-nav">
            <Link href="#">
                <i class="fa fa-home"></i> <span :class="hidden">Home</span>
            </Link>
            <Link href="#">
                <i class="fa fa-question"></i> <span :class="hidden">About Us</span>
            </Link>
            <Link href="#">
                <i class="fa-solid fa-cart-shopping"></i> <span :class="hidden">Products</span>
            </Link>
            <Link href="#">
                <i class="fa-regular fa-images"></i> <span :class="hidden">Gallery</span></Link>
            <Link href="#">
                <i class="fa-solid fa-phone-volume"></i> <span :class="hidden">Contact Us</span></Link>
        </div> -->

        <MainNav :hidden="hide"></MainNav>
    </div>
    <div id="container" class="flex-1">
        <slot />
    </div>
</div>

</template>