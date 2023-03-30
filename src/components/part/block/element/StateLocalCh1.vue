<template>
    <div class="d-flex justify-content-center align-items-center row-height-28">
        <span class="mw-16">
            <span v-if="!rxStateLocCh1">
                <svg v-if="rxReceiveLocCh1"
                    xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-arrow-left" viewBox="0 0 16 16">
                        <path fill-rule="evenodd" d="M15 8a.5.5 0 0 0-.5-.5H2.707l3.147-3.146a.5.5 0 1 0-.708-.708l-4 4a.5.5 0 0 0 0 .708l4 4a.5.5 0 0 0 .708-.708L2.707 8.5H14.5A.5.5 0 0 0 15 8z"/>
                </svg>
            </span>
        </span>
        <span class="d-flex align-items-center justify-content-center badge bg-success mx-1 w-26 h-28">A</span>
        <span class="mw-16">
            <span v-if="!txStateLocCh1">
                <svg v-if="txTransmitLocCh1"
                    xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-arrow-right" viewBox="0 0 16 16">
                    <path fill-rule="evenodd" d="M1 8a.5.5 0 0 1 .5-.5h11.793l-3.147-3.146a.5.5 0 0 1 .708-.708l4 4a.5.5 0 0 1 0 .708l-4 4a.5.5 0 0 1-.708-.708L13.293 8.5H1.5A.5.5 0 0 1 1 8z"/>
                </svg>

                <svg v-else
                    xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-x" width="16" height="16" viewBox="0 0 24 24" stroke-width="1.5" stroke="#7f5345" fill="none" stroke-linecap="round" stroke-linejoin="round">
                        <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
                        <line x1="18" y1="6" x2="6" y2="18" />
                        <line x1="6" y1="6" x2="18" y2="18" />
                </svg>
            </span>
        </span>
    </div>
</template>

<script setup>
    import { onMounted, ref } from "vue";
    import { useCounterStore } from '@/stores/statusData';
    const store = useCounterStore();

    // tx
    let txStateLocCh1 = ref(false);
    let txTransmitLocCh1 = ref(false);

    // rx
    let rxStateLocCh1 = ref(false);
    let rxReceiveLocCh1 = ref(false);

    onMounted(() => {

        let headerCells = Array.from(document.getElementById('headerLocCh1').children);

        // RX row state (arrow)
        rxStateLocCh1.value = headerCells.every(el => el.textContent === 'n/a');

        // RX
        if (!rxStateLocCh1.value) {
            rxReceiveLocCh1.value = store.getMse(0) !== 0;
        }

        // TX row state
        txStateLocCh1.value = headerCells.every(el => el.textContent === 'n/a');

        // TX
        if (!txStateLocCh1.value) {
            txTransmitLocCh1.value = store.getMute(0) === 0;
        }
    });


</script>