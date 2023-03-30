<template>
    <div class="d-flex flex-column row-height-28 text-center">
        <NameMode />
        <AcmCh1 v-if="store.getChannel !== 2" />
        <AcmCh2 v-if="store.getChannel !== 1" />
        <NameDiversity />
    </div>
</template>

<script setup>
    import NameMode      from '@/components/part/block/element/NameMode.vue';
    import AcmCh1        from '@/components/part/block/element/AcmCh1.vue';
    import AcmCh2        from '@/components/part/block/element/AcmCh2.vue';
    import NameDiversity from '@/components/part/block/element/NameDiversity.vue';

    import { useCounterStore } from '@/stores/statusData';
    const store = useCounterStore();

</script>