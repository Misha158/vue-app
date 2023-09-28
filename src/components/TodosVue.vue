<script setup lang="ts">
import type { PropType } from 'vue'

defineProps({
  todos: {
    type: Array as PropType<Array<{ id: number; title: string }>>,
    required: true
  }
})
</script>

<template>
  <div :style="{ 'margin-top': '30px' }">
    <div class="greetings">
      <div>Todos page</div>
      <div v-for="todo in todos" :key="todo.id">
        <div>{{ todo.title }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
