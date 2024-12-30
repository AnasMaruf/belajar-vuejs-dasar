<template>
  <h1 v-bind="data">{{ hello }}</h1>
  <div :class="data.class" v-html="hello"></div>
  <button :disabled="buttonDisabled">This is button</button>
</template>

<script setup>
console.log("Hello Vue");
const hello = "<b>Hello Vue</b>";
const data = {
  class: "hello",
  id: "hello",
};
const buttonDisabled = true;
</script>

<style scoped>
.hello {
  color: green;
}
</style>
