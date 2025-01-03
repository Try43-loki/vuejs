<template>
  <div class="flex justify-center items-center">
    <section class="mt-5 w-[300px] p-3 bg-gray-100 rounded-md">
      <h1 class="text-xl font-semibold">Todo List</h1>

      <form action="" @submit.prevent="addTask" class="flex mt-2">
        <input
        v-model="textTask"
          type="text"
          class="flex-1 border-2 border-gray-300 rounded-s-md border-e-0 px-2 py-1 caret-blue-500 font-light text-blue-500 outline-none focus:border-2 focus:border-blue-400 focus:shadow-sm focus:shadow-blue-500/50 transition-all"
          placeholder="Enter task" 
        />
        <button
        type="submit"
          class="px-2 py-1 rounded-s-none rounded-e-md bg-blue-500 text-white active:bg-blue-400 transition-all"
        >
          Add Task
        </button>
      </form>

      <ul class="mt-2">
        <li
          class="flex justify-between items-center p-2 bg-white shadow-md text-gray-700 rounded-md"
        >
          Build project
          <div class="flex">
            <button
              class="px-2 py-1 text-white rounded-s-md bg-green-500 active:bg-green-400"
            >
              Edit
            </button>
            <button
              class="px-2 py-1 text-white rounded-e-md bg-gray-500 active:bg-gray-400"
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
const textTask = ref("");
const addTask =()=>{
  if(textTask.value == ''){
    alert("Please input a task");
    
  }
}

</script>

<style scoped></style>
