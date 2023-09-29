<script setup lang="ts">
import { ref } from 'vue'

const title = ref('')
const body = ref('')

const emit = defineEmits(['createNewTodo'])

const addNewTodoHandler = () => {
  const newTodo = {
    title: title.value,
    id: Date.now()
  }

  emit('createNewTodo', newTodo)
}
</script>

<template>
  <div :style="{ 'margin-top': '30px' }">
    <form @submit.prevent="addNewTodoHandler">
      <input
        type="text"
        v-model="title"
        @input="title = $event.target?.value"
        placeholder="title"
      />
      <input type="text" v-model="body" @input="body = $event.target?.value" placeholder="body" />

      <button>Sumbit</button>
    </form>
  </div>
</template>

<style scoped></style>
