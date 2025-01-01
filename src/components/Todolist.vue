<template>
  <h1>Todolist</h1>
  <ul>
    <li v-for="item in items" :key="item.id">{{ item.text }}</li>
  </ul>
</template>

<script setup>
const items = [
  {
    id: 1,
    text: "Learn Vue 3",
  },
  {
    id: 2,
    text: "Master Vue Router",
  },
  {
    id: 3,
    text: "Learn Vue Pinia",
  },
];
</script>

<style lang="scss" scoped></style>
