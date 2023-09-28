<script setup lang="ts">
import { ref, defineProps } from 'vue'

const { addNewTodo } = defineProps({
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

  addNewTodo?.(newTodo)
}
</script>

<template>
  <div :style="{ 'margin-top': '30px' }">
    <form @submit.prevent="addNewTodoHandler">
      <input
        type="text"
        v-model="title"
        @input="title = ($event.target as HTMLInputElement)?.value"
        placeholder="title"
      />
      <input
        type="text"
        v-model="body"
        @input="body = ($event.target as HTMLInputElement)?.value"
        placeholder="body"
      />

      <button>Sumbit</button>
    </form>
  </div>
</template>

<style scoped></style>
