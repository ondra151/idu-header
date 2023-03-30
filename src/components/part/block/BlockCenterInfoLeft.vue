<template>
    <div 
        class="d-flex flex-column row-height-28 ms-1"
        :class="[ store.getChannel === 2 ? 'block-order' : '']"
    >
        <NameLocalCh1       v-if="store.getChannel !== 2" />
        <ModulationLocalCh1 v-if="store.getChannel !== 2" />
        <ModulationLocalCh2 v-if="store.getChannel !== 1" />
        <NameLocalCh2       v-if="store.getChannel !== 1" />
    </div>
</template>

<script setup>
    import NameLocalCh1        from '@/components/part/block/element/NameLocalCh1.vue';
    import ModulationLocalCh1  from '@/components/part/block/element/ModulationLocalCh1.vue';
    import ModulationLocalCh2  from '@/components/part/block/element/ModulationLocalCh2.vue';
    import NameLocalCh2        from '@/components/part/block/element/NameLocalCh2.vue';

    import { useCounterStore } from '@/stores/statusData';
    const store = useCounterStore();
</script>