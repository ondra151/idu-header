<template>
    <div 
        class="d-flex flex-column text-center row-height-28 mtop-1 me-1"
        :class="[ store.getChannel === 2 ? 'block-order' : '']"
    >
        <WriteRemoteCh1 v-if="store.getChannel !== 2" />
        <StateRemoteCh1 v-if="store.getChannel !== 2" />
        <StateRemoteCh2 v-if="store.getChannel !== 1" />
        <WriteRemoteCh2 v-if="store.getChannel !== 1" />
    </div>
</template>

<script setup>
    import WriteRemoteCh1 from '@/components/part/block/element/WriteRemoteCh1.vue';
    import WriteRemoteCh2 from '@/components/part/block/element/WriteRemoteCh2.vue';
    import StateRemoteCh1 from '@/components/part/block/element/StateRemoteCh1.vue';
    import StateRemoteCh2 from '@/components/part/block/element/StateRemoteCh2.vue';

    import { useCounterStore } from '@/stores/statusData';
    const store = useCounterStore();

</script>