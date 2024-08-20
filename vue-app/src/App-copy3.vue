<!-- Composition API Short Form-->
<!-- ref is like useState in react -->

<script setup>
import { ref } from "vue";

const name = ref("Subham Bhandari");
const status = ref("free");
const message = ref("Hello! Welcome");
const tasks = ref(["brush", "college", "intern"]);
const link = ref("https://google.com");
const newTask = ref("Some Task");

const toggleStatus = () => {
  if (status.value === "busy") {
    status.value = "free";
  } else if (status.value === "free") {
    status.value = "busy";
  } else {
    status.value = "haha";
  }
};

const addTask = () => {
  if (newTask.value.trim() !== "") {
    tasks.value.push(newTask.value);
    newTask.value = "";
  }
};

const deleteTask = (index) => {
  tasks.value.splice(index, 1);
};
</script>

<template>
  <h1>{{ message }}</h1>
  <p v-if="status === 'free'">User is free</p>
  <p v-else-if="status === 'busy'">User is busy</p>
  <p v-else>User is inactive</p>

  <form @submit.prevent="addTask">
    <label for="newTask">Add Task</label>
    <input type="text" id="newTask" name="newTask" v-model="newTask" />
    <button type="submit">Submit</button>
  </form>

  <h3>Tasks:</h3>
  <ul>
    <li v-if="tasks.length === 0">No Tasks</li>
    <li v-for="(task, index) in tasks" :key="task">
      <span>{{ task }}</span>
      <button @click="deleteTask(index)">Delete</button>
    </li>
  </ul>

  <!-- Attribute binding in vue -->
  <!-- <a v-bind:href="link">Visit Google</a> -->
  <a :href="link">Visit Google</a>
  <br />
  <!-- <button v-on:click="toggleStatus">Change Status</button> -->
  <button @click="toggleStatus">Change Status</button>
</template>
