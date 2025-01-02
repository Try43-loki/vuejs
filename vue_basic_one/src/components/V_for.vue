<template>
  <div class="px-10">
    <ul>
      <li v-for="score in scores">
        <p v-if="score >= 90 && score < 100">Score : {{score}} -> Your Grade is A</p>
        <p v-else-if="score >= 80 && score < 90">Score : {{score}} -> Your Grade is B</p>
        <p v-else-if="score >= 70 && score < 80">Score : {{score}} -> Your Grade is C</p>
        <p v-else-if="score >= 60 && score < 70">Score : {{score}} -> Your Grade is D</p>
        <p v-else-if="score >= 50 && score < 60">Score : {{score}} -> Your Grade is E</p>
        <p v-else="score < 50">Your Grade is</p>
      </li>
    </ul>

    <!-- <form action="">
            <input type="number" v-model="score" placeholder="Enter your score" class="outline-none px-2 py-1 border border-gray-400 rounded-md mt-2">
        </form> -->
  </div>
</template>

<script setup>
import { ref } from "vue";
// const score = ref(null);
const scores = [90, 50, 80, 88, 67, 83];
const fruits = ref(["Mango", "Banana", "Grape", "Apple"]);
</script>

<style scoped></style>
