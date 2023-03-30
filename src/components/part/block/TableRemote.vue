<template>
    <div>
        <table class="table table-bordered text-center table-sm mb-1">
            <tbody>
                <tr>
                    <th>RxL</th>
                    <th>MSE</th>
                    <th>TxP</th>
                    <th>TxF</th>
                </tr>
                <tr v-if="store.getChannel !== 2">
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getRxl(store.isSwap ? 3 : 2), 2)) }">
                        {{ store.setValueHeaderCell(store.getRxl(store.isSwap ? 3 : 2), 2) }}
                    </td> 
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getMse(store.isSwap ? 3 : 2), 2)) }">
                        {{ store.setValueHeaderCell(store.getMse(store.isSwap ? 3 : 2), 2) }} -- 
                    </td>
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getTxp(store.isSwap ? 3 : 2), 1)) }">
                        {{ store.setValueHeaderCell(store.getTxp(store.isSwap ? 3 : 2), 1) }}
                    </td>
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getTxf(store.isSwap ? 3 : 2))) }">
                        {{ store.setValueHeaderCell(store.getTxf(store.isSwap ? 3 : 2)) }}
                    </td>
                </tr>
                <tr v-if="store.getChannel !== 1">
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getRxl(store.isSwap ? 2 : 3), 2)) }">
                        {{ store.setValueHeaderCell(store.getRxl(store.isSwap ? 2 : 3), 2) }}
                    </td>
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getMse(store.isSwap ? 2 : 3), 2)) }">
                        {{ store.setValueHeaderCell(store.getMse(store.isSwap ? 2 : 3), 2) }}
                    </td>
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getTxp(store.isSwap ? 2 : 3), 1)) }">
                        {{ store.setValueHeaderCell(store.getTxp(store.isSwap ? 2 : 3), 1) }}
                    </td>
                    <td :class="{ 'unavailable': store.setClassHeaderCell(store.setValueHeaderCell(store.getTxf(store.isSwap ? 2 : 3))) }">
                        {{ store.setValueHeaderCell(store.getTxf(store.isSwap ? 2 : 3)) }}
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script setup>
    import { useCounterStore } from '@/stores/statusData';
    import { ref } from 'vue';

    const store = useCounterStore();

    const counter = ref(59)

</script>
