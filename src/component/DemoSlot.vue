<template>
    <div class="demoSlot">
        <demo-tabs title='tiêu đề của tabs'></demo-tabs>
    </div>

</template>

<script>

import DemoTabs from './DemoTabs.vue';

export default {
    name: "demo-slot",
    data() {
        return {

        }
    },
    components: {
        DemoTabs
    }
}
</script>
<style>
.demoSlot {
        padding: 250px;
        margin: auto;
        border: 1px solid rgb(0, 0, 0);
    }
</style>