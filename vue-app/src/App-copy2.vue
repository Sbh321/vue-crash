<!-- Composition API -->

<script>
import { ref } from "vue";

export default {
  setup() {
    const name = ref("Subham Bhandari");
    const status = ref("free");
    const message = ref("Hello! Welcome");
    const tasks = ref(["brush", "college", "intern"]);
    const link = ref("https://google.com");

    const toggleStatus = () => {
      if (status.value === "busy") {
        status.value = "free";
      } else if (status.value === "free") {
        status.value = "busy";
      } else {
        status.value = "haha";
      }
    };

    return {
      name,
      status,
      message,
      tasks,
      link,
      toggleStatus,
    };
  },
};
</script>

<template>
  <h1>{{ message }}</h1>
  <p v-if="status === 'free'">User is free</p>
  <p v-else-if="status === 'busy'">User is busy</p>
  <p v-else>User is inactive</p>
  <h3>Tasks:</h3>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>

  <!-- Attribute binding in vue -->
  <!-- <a v-bind:href="link">Visit Google</a> -->
  <a :href="link">Visit Google</a>
  <br />
  <!-- <button v-on:click="toggleStatus">Change Status</button> -->
  <button @click="toggleStatus">Change Status</button>
</template>
