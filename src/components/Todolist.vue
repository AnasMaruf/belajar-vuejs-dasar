<template>
  <h1>Todolist</h1>
  <template v-for="item in items">
    <ul :key="item.id" v-if="!item.done">
      <li v-for="(value, key) in item" :key="key">{{ key }} : {{ value }}</li>
    </ul>
  </template>

  <div v-for="i in 10" :key="i">
    <h1>Hello {{ i }}</h1>
  </div>
</template>

<script setup>
const items = [
  {
    id: 1,
    text: "Learn Vue 3",
    done: true,
  },
  {
    id: 2,
    text: "Master Vue Router",
    done: false,
  },
  {
    id: 3,
    text: "Learn Vue Pinia",
    done: false,
  },
];
</script>

<style lang="scss" scoped></style>
