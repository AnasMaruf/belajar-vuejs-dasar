<template>
  <div>
    <button @click="currentPage = 'about'">About</button>
    <button @click="currentPage = 'blog'">blog</button>
    <button @click="currentPage = 'contact'">contact</button>
    <component :is="pages[currentPage]" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import About from "./About.vue";
import Blog from "./Blog.vue";
import Contact from "./Contact.vue";

const currentPage = ref("about");
const pages = {
  about: About,
  blog: Blog,
  contact: Contact,
};
</script>

<style scoped></style>
