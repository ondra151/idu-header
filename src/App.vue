<script setup>
    import { RouterLink, RouterView } from 'vue-router'
    import Header from '@/components/Header.vue';
</script>

<template>
    <div class="container">
        <header>
            <Header />
        </header>

        <RouterView />
    </div>
</template>

<style scoped>

</style>
