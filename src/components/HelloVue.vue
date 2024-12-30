<template>
  <h1 :id="id" v-bind:class="classHello">{{ hello }}</h1>
  <div :class="classHello" v-html="hello"></div>
  <button :disabled="buttonDisabled">This is button</button>
</template>

<script setup>
console.log("Hello Vue");
const hello = "<b>Hello Vue</b>";
const classHello = "hello";
const id = "hello";
const buttonDisabled = true;
</script>

<style scoped>
.hello {
  color: green;
}
</style>
