<template>
    <div 
        class="d-flex flex-column align-items-end row-height-28 me-1"
        :class="[ store.getChannel === 2 ? 'block-order' : '']"
    >
        <NameRemoteCh1        v-if="store.getChannel !== 2" />
        <ModulationRemoteCh1  v-if="store.getChannel !== 2" />
        <ModulationRemoteCh2  v-if="store.getChannel !== 1" />
        <NameRemoteCh2        v-if="store.getChannel !== 1" />
    </div>
</template>

<script setup>
    import NameRemoteCh1        from '@/components/part/block/element/NameRemoteCh1.vue';
    import ModulationRemoteCh1  from '@/components/part/block/element/ModulationRemoteCh1.vue';
    import ModulationRemoteCh2  from '@/components/part/block/element/ModulationRemoteCh2.vue';
    import NameRemoteCh2        from '@/components/part/block/element/NameRemoteCh2.vue';

    import { useCounterStore } from '@/stores/statusData';
    const store = useCounterStore();

</script>