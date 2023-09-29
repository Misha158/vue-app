<script setup lang="ts">
import { ref } from 'vue'
import type { PropType } from 'vue'

defineProps({
  todos: {
    type: Array as PropType<Array<{ id: number; title: string }>>,
    required: true
  }
})

const emit = defineEmits(['deleteTodo', 'updateTodo'])
const isShowUpdateInput = ref(0)
const newTitle = ref('')

const onDeleteTodo = (id: number) => {
  emit('deleteTodo', id)
}

const onUpdateTodo = (id: number) => {
  isShowUpdateInput.value = id
}

const onSaveUpdatedTodo = (id: number, title: string) => {
  emit('updateTodo', id)
  isShowUpdateInput.value = 0
}
</script>

<template>
  <div :style="{ 'margin-top': '30px' }">
    <div class="greetings">
      <div>Todos page</div>
      <div v-for="todo in todos" :key="todo.id">
        <div class="todo__container">
          <div class="todo">
            <div>{{ todo.id }}.</div>
            <div class="title" v-show="!isShowUpdateInput || isShowUpdateInput !== todo.id">
              {{ todo.title }}
            </div>
            <div class="title" v-show="isShowUpdateInput === todo.id">
              <input v-model="todo.title" @input="newTitle = $event.target?.value" />
              <button @click="onSaveUpdatedTodo(todo.id, newTitle)">Save</button>
            </div>
          </div>
          <div class="actions">
            <button @click="onDeleteTodo(todo.id)">Delete</button>
            <button @click="onUpdateTodo(todo.id)">Update</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.todo__container {
  display: flex;
  flex-direction: column;
  width: 150px;
  background-color: aquamarine;
  border-radius: 5px;
  color: black;
  margin: 10px 0;
  padding: 10px;
}

.todo {
  display: flex;
}

.title {
  margin-left: 5px;
}

.actions {
  background-color: bisque;
  border-radius: 5px;
}
</style>
