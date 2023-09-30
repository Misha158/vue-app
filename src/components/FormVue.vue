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
  <div :style="{ 'margin-top': '30px', width: '500px', padding: '10px' }">
    <v-form @submit.prevent="addNewTodoHandler">
      <v-text-field v-model="title" label="Title of new todo" required hide-details></v-text-field>
      <v-text-field v-model="body" label="Body of new todo" required hide-details></v-text-field>

      <v-btn type="submit">Submit</v-btn>
    </v-form>
  </div>
</template>

<style scoped></style>
