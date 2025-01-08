<template>
  <div>
    <h1>{{ title }}</h1>
    <div>
      <slot name="header" :counter="counter">
        <h1>Default Header</h1>
      </slot>
    </div>
    <div>
      <slot v-if="slots.default" :counter="counter">
        <p>Anda belum mengisi contentnya</p>
      </slot>
    </div>
    <div>
      <slot name="footer" :counter="counter">
        <p>Default Footer</p>
      </slot>
    </div>
  </div>
  <div>
    <button @click="counter++">Increment Counter</button>
  </div>
</template>

<script setup>
import { ref, useSlots } from "vue";

// const { title } = defineProps({
//   title: String,
// });
const slots = useSlots();
const counter = ref(0);
</script>

<style scoped></style>
