<!--Using Watcher -->
<!-- <template>
  <div>
    <h1>Vue.js Watcher Example with Composition API</h1>
    <input v-model="message" placeholder="Type something" />
    <p>Message: {{ message }}</p>
    <p>Reversed Message: {{ reversedMessage }}</p>
  </div>
</template>

<script setup>
import { ref, watch } from "vue";

const message = ref("");
const reversedMessage = ref("");

watch(message, (newValue, oldValue) => {
  reversedMessage.value = newValue.split("").reverse().join("");
  console.log(`Message changed from "${oldValue}" to "${newValue}"`);
});
</script>

<style scoped>
input {
  padding: 8px;
  margin-bottom: 10px;
}
</style> -->

<!--Using Computed Property -->
<template>
  <div>
    <h1>Vue.js Computed Property Example with Composition API</h1>
    <input v-model="message" placeholder="Type something" />
    <p>Message: {{ message }}</p>
    <p>Reversed Message: {{ reversedMessage }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const message = ref("");

// Define a computed property that reverses the message
const reversedMessage = computed(() => {
  return message.value.split("").reverse().join("");
});
</script>

<style scoped>
input {
  padding: 8px;
  margin-bottom: 10px;
}
</style>
