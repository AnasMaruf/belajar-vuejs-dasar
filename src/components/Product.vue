<template>
  <div>
    <label for="productId">
      Product Id
      <select v-model="productId">
        <option value=""></option>
        <option value="product1">Product 1</option>
        <option value="product2">Product 2</option>
        <option value="product3">Product 3</option>
      </select>
    </label>

    <div v-if="product">
      <ProductDetail
        :id="product.id"
        :price="product.price"
        :name="product.name"
      />
      <!-- <h1>Product</h1>
      <p>Id: {{ product.id }}</p>
      <p>Name: {{ product.name }}</p>
      <p>Price: {{ product.price }}</p> -->
    </div>
  </div>
</template>

<script setup>
import { onWatcherCleanup, ref, watch, watchEffect } from "vue";
import ProductDetail from "./ProductDetail.vue";

const productId = ref("product1");
const product = ref(null);

// watch(
//   productId,
//   async (newVal, oldVal) => {
//     const response = await fetch(`/${newVal}.json`);
//     product.value = await response.json();
//   },
//   {
//     immediate: true,
//   }
// );

watchEffect(async (newVal, oldVal) => {
  onWatcherCleanup(() => {
    console.log("cleanup");
  });
  const response = await fetch(`/${productId.value}.json`);
  product.value = await response.json();
});
</script>

<style scoped></style>
