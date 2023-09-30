<script lang="ts" setup=""></script>

<template>
  <v-layout class="rounded rounded-md">
    <v-app-bar color="primary" density="compact" title="Todolist"></v-app-bar>

    <v-main class="d-flex" style="min-height: 300px">
      <slot></slot>
    </v-main>
  </v-layout>
</template>

<style scoped></style>
