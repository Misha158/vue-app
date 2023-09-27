<script setup lang="ts">
import { onMounted, ref } from 'vue'

const counter = ref(0)

const increment = () => {
  counter.value++
}

const decrement = () => {
  counter.value--
}

// lifecycle hooks
onMounted(() => {
  console.log(`The initial count is ${counter.value}.`)
})
</script>

<template>
  <div class="greetings">
    <div>Counter page</div>
    <button @click="increment">Increment</button>
    <button @click="decrement">Decrement</button>
    <div>Counter: {{ counter }}</div>
  </div>
</template>

<style scoped></style>
