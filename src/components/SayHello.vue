<template>
  <div>
    <input type="text" placeholder="First Name" id="firstName" /><br />
    <input type="text" placeholder="Last Name" id="lastName" /><br />
    <button v-on:click="sayHello">Say Hello</button>
  </div>
  <h1>Hello {{ person.firstName }} {{ person.lastName }}</h1>
</template>

<script setup>
import { reactive } from "vue";

const person = reactive({
  firstName: "",
  lastName: "",
});

function sayHello() {
  person.firstName = document.getElementById("firstName").value;
  person.lastName = document.getElementById("lastName").value;
}
</script>

<style scoped></style>
