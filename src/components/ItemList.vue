<template>
  <div>
    <h2>TODOリスト</h2>
    <div>
      <h3>未完了タスク</h3>
      <div v-for="task in tasks" :key="task.name">
        <div v-if="task.isFinished === false" class="task">
          <div class="name">{{ task.name }}</div>
          <button @click="finishTask(task.id)">完了！</button>
        </div>
      </div>
    </div>
    <div>
      <h3>完了タスク</h3>
      <div v-for="task in tasks" :key="task.name">
        <div v-if="task.isFinished === true" class="task">
          <div class="name">{{ task.name }}</div>
        </div>
      </div>
    </div>
    <div>
      <label>
        名前
        <input v-model="newTaskName" type="text" />
      </label>
      <button @click="addTask">add</button>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const newId = ref(2);

    const tasks = ref([
      { id: 0, name: "たまご", isFinished: false },
      { id: 1, name: "りんご", isFinished: false },
    ]);
    const newTaskName = ref("");

    const addTask = () => {
      if (newTaskName.value === "") {
        alert("名前を入力してください");
      } else {
        tasks.value.push({
          id: newId.value,
          name: newTaskName.value,
          isFinished: false,
        });
        newTaskName.value = "";
        newId.value = newId.value + 1;
      }
    };

    const finishTask = (id) => {
      tasks.value.forEach((value) => {
        if (value.id === id) {
          value.isFinished = true;
        }
      });
    };

    return { tasks, newTaskName, addTask, finishTask };
  },
};
</script>

<style></style>
