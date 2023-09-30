<script lang="ts" setup="">
import { ref } from 'vue'
const { textBtn } = defineProps({
  textBtn: String
})

const dialog = ref(false)
</script>

<template>
  <div class="text-center">
    <v-btn color="primary">
      {{ textBtn }}

      <v-dialog v-model="dialog" activator="parent" width="auto">
        <v-card>
          <slot></slot>
          <v-card-actions>
            <v-btn color="primary" block @click="dialog = false">Close Dialog</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-btn>
  </div>
</template>

<style scoped></style>
