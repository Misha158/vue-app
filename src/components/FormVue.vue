<script setup lang="ts">
import { ref, defineProps } from 'vue'

const props = defineProps({
  addNewTodo: {
    type: Function
  }
})

const title = ref('')
const body = ref('')

const addNewTodoHandler = () => {
  const newTodo = {
    title: title.value,
    id: Date.now()
  }

  props.addNewTodo?.(newTodo)
}
</script>

<template>
  <form @submit.prevent="addNewTodoHandler">
    <input
      type="text"
      v-bind:value="title"
      @input="title = ($event.target as HTMLInputElement)?.value"
      placeholder="title"
    />
    <input
      type="text"
      v-bind:value="body"
      @input="body = ($event.target as HTMLInputElement)?.value"
      placeholder="body"
    />
    <button>Sumbit</button>
  </form>
</template>

<style scoped></style>
