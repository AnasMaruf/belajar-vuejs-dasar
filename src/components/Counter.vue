<template>
  <div>
    <h1 id="count">Counter : {{ count }}</h1>
    <button v-on:click="increment">Increment</button>
  </div>
</template>

<script setup>
let count = 0;
function increment() {
  count++;

  document.getElementById("count").innerText = `Counter : ${count}`;
}
</script>

<style scoped></style>
