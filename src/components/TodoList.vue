<template>
  <div class="flex justify-center items-center">
    <section class="mt-5 w-[350px] p-3 bg-gray-100 rounded-md">
      <h1 class="text-xl font-semibold">Todo List</h1>

      <form action="" @submit.prevent="addTask" class="flex mt-2">
        <input
          v-model="textTask"
          type="text"
          class="flex-1 border-2 border-gray-300 rounded-s-md border-e-0 p-2 caret-blue-500 text-blue-500 outline-none focus:border-2 focus:border-blue-400 focus:shadow-sm focus:shadow-blue-500/50 transition-all"
          placeholder="Enter task"
        />
        <button
          type="submit"
          class="p-2 rounded-s-none rounded-e-md bg-blue-500 text-white active:bg-blue-400 transition-all"
        >
          {{ isEdit ? "Update" : "Add Task" }}
        </button>
      </form>

      <ul class="mt-2">
        <li
          v-for="(task, index) in tasks"
          class="mt-2 flex justify-between items-center p-2 bg-white shadow-md text-gray-700 rounded-md"
        >
          <span class="font-semibold">{{ task }}</span>
          <div class="flex">
            <button
              @click="editTask(index)"
              class="p-2 text-white rounded-s-md bg-green-500 active:bg-green-400"
            >
              Edit
            </button>
            <button
              @click="removeTask(index)"
              class="p-2 text-white rounded-e-md bg-gray-500 active:bg-gray-400"
            >
              Delete
            </button>
          </div>
        </li>
      </ul>
    </section>
  </div>
</template>

<script setup>
import { ref } from "vue";
const tasks = ref([]);
const editTaskIndex = ref(null);
const textTask = ref("");
let isEdit = ref(false);

const addTask = () => {
  if (textTask.value.trim() === "") {
    alert("Please input a task");
    return;
  }

  if (editTaskIndex.value !== null) {
    tasks.value[editTaskIndex.value] = textTask.value.trim();
    editTaskIndex.value = null;
    isEdit.value = !isEdit.value;
  } else {
    tasks.value.push(textTask.value.trim());
  }
  textTask.value = "";
};
const removeTask = (index) => {
  tasks.value.splice(index, 1);
};
const editTask = (index) => {
  textTask.value = tasks.value[index];
  editTaskIndex.value = index;
  if (isEdit.value == false) {
    isEdit.value = !isEdit.value;
  }
};
</script>

<style scoped></style>
