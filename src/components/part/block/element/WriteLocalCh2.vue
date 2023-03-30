<template>
    <div class="d-flex justify-content-center align-items-center order-top">
        <span class="badge d-inline-block w-24 h-24 py-1 px-1 fw-bold text-danger border border-danger rounded-circle">W</span>
    </div>
</template>

<script setup>

    import { useCounterStore } from '@/stores/statusData';
    const store = useCounterStore();
</script>

