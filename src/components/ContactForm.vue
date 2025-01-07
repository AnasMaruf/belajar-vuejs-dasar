<template>
  <div>
    <h1>Contact Us</h1>
    <form>
      <div>
        <label for="name"
          >Name
          <input type="text" id="name" v-model="model.name" />
        </label>
      </div>
      <div>
        <label for="email"
          >Email
          <input type="text" id="email" v-model="model.email" />
        </label>
      </div>
      <div>
        <label for="age"
          >Age
          <input type="text" id="age" v-model="model.age" />
        </label>
      </div>
      <div>
        <label for="type">
          <select name="type" id="type" v-model="model.type">
            <option value="Regular">Regular</option>
            <option value="VIP">VIP</option>
          </select>
        </label>
      </div>
      <div>
        <label for="complain"
          >Complain
          <input type="checkbox" id="complain" v-model="model.complain" />
        </label>
      </div>
      <div>
        <label for="message"
          >Message
          <textarea type="text" id="message" v-model="model.message" />
        </label>
      </div>
    </form>
  </div>
</template>

<script setup>
const model = defineModel({
  type: Object,
  required: true,
  get: (value) => {
    value.email = value.email.toUpperCase();
    return value;
  },
});
</script>

<style scoped></style>
