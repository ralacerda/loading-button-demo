<script setup lang="ts">
import { ref } from 'vue'

const loading = ref(false)

const handleAsyncFunction = async () => {
  loading.value = true
  await new Promise(resolve => setTimeout(resolve, 3000))
  loading.value = false
}
</script>

<template>
  <div class="container">
    <h1>Vue Loading Button Example</h1>
    <button @click="handleAsyncFunction" :disabled="loading">
      <span v-if="loading">Loading...</span>
      <span v-else>Click me</span>
    </button>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

button {
  font-size: 1.2em;
  padding: 10px 20px;
  cursor: pointer;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 4px;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #45a049;
}

button:disabled {
  background-color: #cccccc;
  cursor: not-allowed;
}
</style>