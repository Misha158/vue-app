<template>
  <div>Counter page</div>
  <button @click="increment">Increment</button>
  <button @click="decrement">Decrement</button>
  <div>Counter: {{ counter }}</div>
</template>
<script setup lang="ts">
import { ref } from 'vue'

const counter = ref(0)
const increment = () => {
  counter.value++
}

const decrement = () => {
  counter.value--
}
</script>

<style></style>
