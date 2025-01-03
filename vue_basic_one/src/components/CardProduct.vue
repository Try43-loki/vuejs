<template>
  <div>
    <nav
      class="w-4/5 bg-orange-500 h-10 m-auto flex justify-center items-center"
    >
      <ul class="flex justify-center items-center gap-4">
        <li
          v-for="(link, index) in navLinks"
          :key="index"
          @click.prevent="activePage = index"
          class="text-sm cursor-pointer"
          :class="{
            'text-white': activePage === index,
            'hover:text-white': activePage !== index,
          }"
        >
          <a :href="link.links">{{ link.item }}</a>
        </li>
      </ul>
    </nav>
    <div class="w-4/5 relative m-auto">
      <div
        class="text-sm text-white bg-orange-500 rounded-md absolute w-14 h-7 text-center leading-7 top-5 right-0"
      >
        Cart({{ cartItem }})
      </div>
    </div>
    <div class="w-4/5 mt-5 m-auto">
      <div class="bg-gray-100 mt-16 w-[150px] p-2 rounded-md">
        <img
          src="https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?auto=compress&cs=tinysrgb&w=600"
          height="80px"
          width="150px"
          class="object-contain"
          alt=""
        />
        <h2 class="text-sm font-semibold mt-2">Noodle</h2>
        <p class="text-[10px]">Quantity: {{ count }} pice</p>
        <button
          class="text-[10px] text-white bg-orange-500 rounded-md px-3 py-1 w-full"
          @click="countCart"
          :class="count > 0 ? 'bg-orange-500': 'bg-gray-400 cursor-not-allowed' "
        >
          Add to cart
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 10,
      cartItem : 0,
      activePage: 0, // Default active page (Home)
      navLinks: [
        { item: "Home", links: "index.html" },
        { item: "About", links: "about.html" },
        { item: "Contact", links: "contact.html" },
      ],
    };
    
  },
  methods:{
        countCart(){
          this.count -= 1;
          this.cartItem += 1;
        }
      },
};
</script>

<style scoped></style>
