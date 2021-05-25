<template>
  <div>
    <h2>TODOリスト</h2>
    <div v-for="item in items" :key="item.name">
      <div class="item">
        <div class="name">名前: {{ item.name }}</div>
      </div>
    </div>
    <div>
      <label>
        名前
        <input v-model="newItemName" type="text" />
      </label>
      <button @click="addItem">add</button>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const items = ref([
      { name: "たまご"},
      { name: "りんご"},
    ]);
    const newItemName = ref("");

    const addItem = () => {
      if (newItemName.value === "") {
        alert("名前を入力してください");
      } else {
        items.value.push({ name: newItemName.value});
        newItemName.value = "";
      }
    };

    return { items, newItemName, addItem };
  },
};
</script>

<style></style>