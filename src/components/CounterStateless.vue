<template>
  <div>
    <h1>Counter {{ name }} : {{ counter }}</h1>
  </div>
</template>

<script setup>
const { counter, name } = defineProps(["counter", "name"]);
</script>

<style scoped></style>
