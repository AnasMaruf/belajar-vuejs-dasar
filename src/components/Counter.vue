<template>
  <div>
    <h1 id="count">Counter {{ counter.name }} : {{ counter.count }}</h1>
    <button v-on:click="increment">Increment</button>
  </div>
</template>

<script setup>
import { nextTick, ref } from "vue";

let counter = ref({
  count: 0,
  name: "Anas",
});
async function increment() {
  console.log(`Increment counter: ${counter.value.count}`);
  counter.value = {
    name: counter.value.name,
    count: counter.value.count + 1,
  };
  counter.value.count++;
  await nextTick();
  counter.value.count++;
  await nextTick();
  console.log(`Increment count after nextTick`);
}
</script>

<style scoped></style>
