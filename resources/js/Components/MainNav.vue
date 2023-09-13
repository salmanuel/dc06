<script setup>
import { Link } from '@inertiajs/vue3';
import { defineProps } from 'vue';

const {hidden} = defineProps (['hidden'])
</script>

<template>

    <div class="main-nav">
        <Link :href="route('dashboard')" :active="route().current('dashboard')">
            <i class="fa fa-home"></i> <span :hidden="hidden">Dashboard</span>
        </Link>
        <Link :href="route('clients')" :active="route().current('clients')">
            <i class="fa-solid fa-user"></i> <span :hidden="hidden">Clients</span>
        </Link>
    </div>

</template>