<template>
    <div>
        <table class="table table-bordered text-center table-sm mb-1">
            <tbody>
                <tr>
                    <th>TxF 
                        <a href="" @click.prevent="store.setTest1Value">SET</a>
                    </th>
                    <th>TxP</th>
                    <th>MSE</th>
                    <th>RxL</th>
                </tr>
                <tr id="headerLocCh1" v-if="store.getChannel !== 2">
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getTxf(0))) }">
                        {{ store.setValueHeaderCell(store.getTxf(0)) }}
                    </td>
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getTxp(0), 1)) }">
                        {{ store.setValueHeaderCell(store.getTxp(0), 1) }}
                    </td>
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getMse(0), 2)) }">
                        {{ store.setValueHeaderCell(store.getMse(0), 2) }}
                    </td>
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getRxl(0), 2)) }">
                        {{ store.setValueHeaderCell(store.getRxl(0), 2) }}
                    </td>
                </tr>
                <tr id="headerLocCh2" v-if="store.getChannel !== 1">
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getTxf(1))) }">
                        {{ store.setValueHeaderCell(store.getTxf(1)) }}
                    </td>
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getTxp(1), 1)) }">
                        {{ store.setValueHeaderCell(store.getTxp(1), 1) }}
                    </td>
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getMse(1), 2)) }">
                        {{ store.setValueHeaderCell(store.getMse(1), 2) }}
                    </td>
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getRxl(1), 2)) }">
                        {{ store.setValueHeaderCell(store.getRxl(1), 2) }}
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script setup>
    import { storeToRefs } from 'pinia';
    import { useCounterStore } from '@/stores/statusData';
    import { onMounted } from 'vue';

    const store = useCounterStore();

    const { test1, test2 } = storeToRefs(store); // reaktivni pouze na prvni uroven


</script>
