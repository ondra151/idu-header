<template>
    <div 
        class="d-flex flex-column text-center row-height-28 ms-1"
        :class="[ store.getChannel === 2 ? 'block-order' : 'mtop-1']"
    >
        <WriteLocalCh1 v-if="store.getChannel !== 2" />
        <StateLocalCh1 v-if="store.getChannel !== 2" />
        <StateLocalCh2 v-if="store.getChannel !== 1" />
        <WriteLocalCh2 v-if="store.getChannel !== 1" />
    </div>
</template>

<script setup>
    import WriteLocalCh1 from '@/components/part/block/element/WriteLocalCh1.vue';
    import WriteLocalCh2 from '@/components/part/block/element/WriteLocalCh2.vue';
    import StateLocalCh1 from '@/components/part/block/element/StateLocalCh1.vue';
    import StateLocalCh2 from '@/components/part/block/element/StateLocalCh2.vue';

    import { useCounterStore } from '@/stores/statusData';
    const store = useCounterStore();

</script>

<style lang="scss" scoped>

</style>