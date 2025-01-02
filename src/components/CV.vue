<template>
  <div>
    <nav
      class="w-full h-16 bg-orange-500 px-5 flex justify-between items-center"
    >
      <img
        id="logo"
        src="../assets/imgs/unity.png"
        height="40"
        width="40"
        alt="logo"
      />
      <ul class="flex justify-center items-center gap-5">
        <li
          class="font-medium hover:text-white transition-all"
          v-for="(page, index) in pages"
          :key="index"
          @click.prevent="activePage = index"
          :class="{ 'text-white ': activePage === index }"
        >
          <a :href="page.item.href">{{ page.item.text }}</a>
        </li>
      </ul>
      <button
        class="bg-white px-3 py-2 rounded-md font-semibold"
        @click.prevent="toggleDark"
      >
        {{ textMode }}
      </button>
    </nav>
    <!-- Body Content -->
    <section
      class="flex justify-center items-center flex-col "
      :class="{'bg-white' : !isDark , 'bg-black' : isDark}"
      style="height: calc(100vh - 64px)"
    >
      <h1 class="tracking-widest text-blue-500">
        {{ pages[activePage].pageTitle }}
      </h1>
      <p class="tracking-widest text-orange-500">
        {{ pages[activePage].content }}
      </p>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isDark: false,
      textMode: 'Dark',
      activePage: 0,
      pages: [
        {
          item: { text: "Home", href: "home.html" },
          pageTitle: "Welcome to my Web Application",
          content: "This is the home page content",
        },
        {
          item: { text: "About", href: "about.html" },
          pageTitle: "My Name is MEY soytry",
          content: "You are right; this is a Web Application",
        },
        {
          item: { text: "Contact", href: "contact.html" },
          pageTitle: "This is my contact",
          content: "Email: meysoytry@gmail.com",
        },
      ],
    };
  },

  methods: {
  
    toggleDark() {
      this.isDark = !this.isDark;
      this.textMode = this.isDark ? 'Light' : 'Dark';
    },
  },
};
</script>

<style scoped></style>
