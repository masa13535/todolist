<template>
    <div>ItemList</div>
</template>

<script>
import { ref } from "vue";

export default {
    setup() {
        count items = ref([
            { name: "たまご", price: 100 },
            { name: "りんご", price: 160 },
        ]);
        return { items };
    },
};
</script>

<style></style>