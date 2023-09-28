<script setup lang="ts">
import { ref } from 'vue'
import TodosVue from '@/components/TodosVue.vue'
import FormVue from '@/components/FormVue.vue'
import CounterVue from '@/components/CounterVue.vue'

const todos = ref([
  { id: 1, title: 'todo-1' },
  { id: 2, title: 'todo-2' },
  { id: 3, title: 'todo-3' }
])

const addNewTodo = (todo: any) => {
  todos.value.push(todo)
}

const onDeleteTodo = (id: number) => {
  todos.value = todos.value.filter((todo) => todo.id !== id)
}

const onSaveUpdatedTodo = (id: number, title: string) => {
  todos.value = todos.value.map((todo) => {
    if (todo.id === id) {
      return { id: todo.id, title }
    }

    return todo
  })
}
</script>

<template>
  <div class="greetings">
    <CounterVue />
    <FormVue @createNewTodo="addNewTodo" />
    <TodosVue @deleteTodo="onDeleteTodo" @onSaveUpdatedTodo="onSaveUpdatedTodo" :todos="todos" />
  </div>
</template>

<style scoped></style>
