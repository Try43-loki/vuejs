<template>
  <div class="px-10 py-10">
    <form @submit.prevent="addStudent">
      <input
        v-model="nameStudent"
        type="text"
        class="px-2 py-1 border border-gray-300 rounded-md focus:border-gray-400 transition-all outline-none"
        placeholder="Enter Student..."
      />
      <br />
      <input
        v-model="score"
        type="number"
        class="px-2 py-1 border border-gray-300 rounded-md focus:border-gray-400 transition-all outline-none mt-4"
        placeholder="Enter Score..."
      />
      <br />
      <button
        type="submit"
        class="mt-4 px-4 py-2 bg-blue-500 text-white rounded-md hover:bg-blue-600 transition-all"
      >
        Add Student
      </button>
    </form>

    <ul class="mt-6">
      <li v-for="(list, index) in lists" :key="index">
        <span class="font-semibold">{{ list.nameStudent }}</span>
        your score
        <span
          class="text-black"
          :class="{
            'text-red-500': list.score >= 90 && list.score < 100,
            'text-pink-500 ': list.score >= 80 && list.score < 90,
            'text-yellow-500': list.score >= 70 && list.score < 80,
            'text-green-500': list.score >= 60 && list.score < 70,
            'text-blue-600': list.score >= 50 && list.score < 60,
            'text-gray-800': list.score < 50,
          }"
          >{{ list.score }}</span
        >
        you get grade
        <span
          class="text-black"
          :class="{
            'text-red-500': list.score >= 90 && list.score < 100,
            'text-pink-500 ': list.score >= 80 && list.score < 90,
            'text-yellow-500': list.score >= 70 && list.score < 80,
            'text-green-500': list.score >= 60 && list.score < 70,
            'text-blue-600': list.score >= 50 && list.score < 60,
            'text-gray-800': list.score < 50,
          }"
          >{{
            list.score >= 90
              ? "A"
              : list.score >= 80
              ? "B"
              : list.score >= 70
              ? "C"
              : list.score >= 60
              ? "D"
              : list.score >= 50
              ? "E"
              : "F"
          }}</span
        >
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from "vue";

const nameStudent = ref("");
const score = ref(null);
const lists = ref([]);

const addStudent = () => {
  if (nameStudent.value && score.value !== null) {
    lists.value.push({ nameStudent: nameStudent.value, score: score.value });
    nameStudent.value = ""; // Clear input after adding
    score.value = null;
  } else {
    alert("Please fill in both fields before submitting.");
  }
};
</script>

<style scoped></style>
