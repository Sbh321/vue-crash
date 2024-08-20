<!-- Options API -->

<script>
export default {
  data() {
    return {
      message: "Hello!",
      status: "free",
      tasks: ["brush", "college", "intern"],
      link: "https://google.com",
    };
  },
  methods: {
    toggleStatus() {
      if (this.status === "busy") {
        this.status = "free";
      } else if (this.status === "free") {
        this.status = "busy";
      } else {
        this.status = "haha";
      }
    },
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
    <li v-for="task in tasks">{{ task }}</li>
  </ul>

  <!-- Attribute binding in vue -->
  <!-- <a v-bind:href="link">Visit Google</a> -->
  <a :href="link">Visit Google</a>

  <!-- <button v-on:click="toggleStatus">Change Status</button> -->
  <button @click="toggleStatus">Change Status</button>
</template>
