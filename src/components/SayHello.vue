<template>
  <div>
    <button v-on:click="increment">Increment {{ counter }}</button> <br />
    <input type="text" placeholder="First Name" id="firstName" /><br />
    <input type="text" placeholder="Last Name" id="lastName" /><br />
    <button v-on:click="sayHello">Say Hello</button>
  </div>
  <h1>Hello {{ fullName }}</h1>
</template>

<script setup>
import { computed, reactive, ref } from "vue";

const person = reactive({
  firstName: "",
  lastName: "",
});

function sayHello() {
  person.firstName = document.getElementById("firstName").value;
  person.lastName = document.getElementById("lastName").value;
}

const fullName = computed((oldName) => {
  console.log(`Fullname Called ${oldName}`);
  return `${person.firstName} ${person.lastName}`;
});

const counter = ref(0);
function increment() {
  console.log("Increment called");
  counter.value++;
}
</script>

<style scoped></style>
