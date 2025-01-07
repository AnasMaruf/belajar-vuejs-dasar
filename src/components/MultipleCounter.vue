<template>
  <div>
    <Counter :name="counter1" initial-count="20" />
    <Counter :name="counter2" initial-count="20" />

    <CounterStateless
      name="Anas"
      :counter="counter"
      :increment="1"
      @click="increment"
    />
    <CounterStateless
      name="Eko"
      :counter="counter"
      :increment="2"
      @click="increment"
    />
  </div>
</template>

<script setup>
import { ref } from "vue";
import Counter from "./Counter.vue";
import CounterStateless from "./CounterStateless.vue";
const counter1 = "Anas";
const counter2 = "Eko";

const counter = ref(0);

function increment(value) {
  counter.value += value;
}
</script>

<style scoped></style>
