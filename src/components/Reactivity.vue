<template>
  <div>
    <h1 class="text-cyan-500 text-center">My name is {{ myName }}</h1>
    <a
      class="text-center text-amber-500 ml-10 text-sm"
      title="YouTube"
      :href="6 < count ? link : self"
      >Click here</a
    >
    <img
      v-bind:src="profile"
      class="ml-10"
      height="100px"
      width="100px"
      alt=""
    />
    <p class="ml-10 text-sm">{{ count }}</p>
    <button
      @click="count++"
      class="ml-10 px-2 py-1 text-sm text-white bg-orange-500 rounded-md"
    >
      Increase
    </button>
    <button
      @click="count--"
      class="ml-10 px-2 py-1 text-sm text-white bg-orange-500 rounded-md"
    >
      Decrease
    </button>
    <hr class="mt-5" />
    <p class="ml-10 text-sm mt-2">{{ count }} Product</p>

    <p
      v-if="count > 30"
      class="ml-10 mt-2 bg-orange-500 rounded-md w-[70px] text-center text-sm px-2 py-1 text-white"
    >
      In Stock
    </p>
    <p
      v-else-if="count >= 10 || count > 0"
      class="ml-10 bg-green-700 rounded-md w-[130px] text-center text-sm px-2 py-1 text-white mt-2"
    >
      Almost out stock
    </p>
    <p
      v-else
      class="ml-10 bg-red-700 rounded-md w-[80px] text-center text-sm px-2 py-1 text-white mt-2"
    >
      Out Stock
    </p>
    <div
      class="mt-3 m-auto rounded-sm w-32 h-32 bg-blue-600 flex justify-center items-center"
      :class="isChange ? 'bg-red-600' : 'bg-blue-600'"
    >
      <button
        @click="isChange = !isChange"
        class="px-2 py-1 rounded-md bg-blue-400 text-white text-[10px]"
        :class="isChange ? 'bg-red-400' : 'bg-blue-400'"
      >
        click
      </button>
    </div>
    <hr class="mt-5" />
    <ul class="mt-4 ml-10">
      <li v-for="brand in brands" :key="brand.id" >{{ brand.name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isChange: false,
      count: 0,
      myName: "MEY soytry",
      link: "https://www.youtube.com/watch?v=RuDaGLqtN1M",
      self: "http://localhost:3000/",
      profile:
        "https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?auto=compress&cs=tinysrgb&w=600",
      brands: [
        { id: 1, name: "BWM" },
        { id: 2, name: "Ford" },
        { id: 3, name: "Toyota" },
      ],
    };
  },
};
</script>

<style scoped></style>
