<template>
  <div>
    <h1 class="text-white text-xl font-medium text-center">{{ Brand }}</h1>
    <ul class="mt-5 flex justify-center gap-4 items-center">
      <li class="text-white" v-for="(page, index) in pages" :key="index">
        <a :href="page.item.link" @click.prevent="activePage = index" >{{ page.item.text }}</a>
      </li>
    </ul>
    <h1 class="text-white ml-5 mt-5" >{{pages[activePage].pageTitle}}</h1>
    <p  class="text-white ml-5 mt-5" >{{pages[activePage].content}}</p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      Brand: "Single Page Application",
      activePage: 0,
      pages:[

            {
            item: { text: "Home", link: "home.html" },
            pageTitle : 'Home Page',
            content: 'This is the home page content'
           },
            {
            item: { text: "About", link: "about.html" },
            pageTitle : 'About Page',
            content: 'This is the About page content'
           },
            {
            item: { text: "Contact", link: "contact.html" },
            pageTitle : 'Contact Page',
            content: 'This is the Contact page content'
           },

      ]

    };
  },
};
</script>
<style scoped></style>
