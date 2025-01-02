<template>
  <div>
    <h1 id="count">Counter {{ props.name }} : {{ counter.count }}</h1>
    <button v-on:click="increment">Increment</button>
  </div>
</template>

<script setup>
import { nextTick, ref } from "vue";

const props = defineProps(["name", "initialCount"]);

let counter = ref({
  count: props.initialCount,
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
