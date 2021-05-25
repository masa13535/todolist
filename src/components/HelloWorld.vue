<template>
  <div>
    <h1>{{ msg }}</h1>
    <item-list />
  </div>
</template>

<script>
import ItemList from "./ItemList.vue";

export default {
  components: {
    ItemList,
  },
  props: {
    msg: {
      type: String,
      default: "",
    },
  },
};
</script>
