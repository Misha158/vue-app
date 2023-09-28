<script setup lang="ts">
import { onMounted, ref } from 'vue'
import TodosView from './TodosView.vue'
import FormVue from '@/components/FormVue.vue'

const counter = ref(0)
const todos = ref([
  { id: 1, title: 'todo-1' },
  { id: 2, title: 'todo-2' },
  { id: 3, title: 'todo-3' }
])

const increment = () => {
  counter.value++
}

const decrement = () => {
  counter.value--
}

const addNewTodo = (todo: any) => {
  todos.value.push(todo)
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

    <div :style="{ 'margin-top': '30px' }">
      <TodosView :todos="todos" />
    </div>
    <div :style="{ 'margin-top': '30px' }">
      <FormVue :addNewTodo="addNewTodo" />
    </div>
  </div>
</template>

<style scoped></style>
