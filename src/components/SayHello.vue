<template>
  <div>
    <form action="">
      <button v-on:click="counter++">Increment {{ counter }}</button> <br />
      <input
        type="text"
        placeholder="First Name"
        id="firstName"
        @input="changeFirstName"
      /><br />
      <input
        type="text"
        placeholder="Last Name"
        id="lastName"
        @input="changeLastName"
      /><br />
      <button v-on:click.prevent="sayHello">Say Hello</button>
    </form>
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

function changeFirstName(e) {
  person.firstName = e.target.value;
}

function changeLastName(e) {
  person.lastName = e.target.value;
}
</script>

<style scoped></style>
