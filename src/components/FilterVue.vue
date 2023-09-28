<template>
  <div>
    <label class="label">
      Filter by title
      <input type="text" placeholder="Search for title" @input="filterTodos(($event.target as HTMLInputElement)?.value)" />
    </label>
  </div>
</template>
<script lang="ts" setup>
const { filterTodos } = defineProps({
  filterTodos: {
    type: Function,
    required: true
  }
})
</script>
<style scoped>
.label {
  display: flex;
  flex-direction: column;
  margin-top: 30px;
}
</style>
