<template>
  <div>
    <form action="" class="p-4 rounded-md bg-white">
      <p>My name is {{ name }}</p>
      <p>My age is {{ range > 0 ? range + " Years" : "" }}</p>
      <p class="text-xl">Select Gender : {{ gender }}</p>
      <p>University : {{ school }}</p>
      <label for="male">
        Male
        <input id="male" type="radio" value="male" v-model="gender" />
      </label>
      <br />
      <label for="female">
        Female
        <input id="female" type="radio" value="female" v-model="gender" />
      </label>
      <br />
      <label for="other">
        Other
        <input id="other" type="radio" value="other" v-model="gender" />
      </label>
      <br />
      <input
        class="border outline-none rounded-md text-sm px-2 py-1"
        type="text"
        v-model="name"
        placeholder="Enter your name"
      />
      <br />
      <input type="range" v-model="range" min="0" max="100" />
      <br />
      <select
        v-model="school"
        class="border outline-none rounded-md text-sm px-2 py-1"
      >
        <option disabled value="">You can select</option>
        <option value="AUPP">AUPP</option>
        <option value="RUPP">RUPP</option>
        <option value="ETECT">ETECT</option>
      </select>
      <br />
      <p>Choose your favorite fruits {{ formattedFruits }}</p>
      <br />
      <label for="apple"
        >Apple
        <input type="checkbox" id="apple" value="Apple" v-model="fruits" />
      </label>
      <br />
      <label for="banana"
        >Banana
        <input type="checkbox" id="banana" value="Banana" v-model="fruits" />
      </label>
      <br />
      <label for="grape"
        >Grape
        <input type="checkbox" id="grape" value="Grape" v-model="fruits" />
      </label>
    </form>
  </div>
</template>

<script setup>
import { ref , computed } from "vue";
const name = ref("");
const gender = ref("");
const range = ref(0);
const school = ref("");
const fruits = ref([]);
const formattedFruits = computed(() => {
      return fruits.value.join(", "); // Join the array without quotes
    });
</script>

<style lang="scss" scoped></style>
