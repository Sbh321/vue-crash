<script>
export default {
  data() {
    return {
      message: "Hello!",
      status: "haha",
      tasks: ["brush", "college", "intern"],
      link: "https://google.com",
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
    <li v-for="task in tasks">{{ task }}</li>
  </ul>

  <!-- Attribute binding in vue -->
  <a v-bind:href="link">Visit Google</a>
</template>
