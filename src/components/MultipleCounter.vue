<template>
  <div>
    <Counter :name="counter1" initial-count="20" />
    <Counter :name="counter2" initial-count="20" />

    <CounterStateless name="Anas" :counter="counter" />
    <CounterStateless name="Eko" :counter="counter" />
    <button @click="counter++">Increment Counter</button>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Counter from "./Counter.vue";
import CounterStateless from "./CounterStateless.vue";
const counter1 = "Anas";
const counter2 = "Eko";

const counter = ref(0);
</script>

<style scoped></style>
