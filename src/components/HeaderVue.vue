<script lang="ts" setup=""></script>

<template>
  <v-card class="mx-auto" max-width="448">
    <v-layout>
      <v-app-bar color="primary" density="compact">
        <template v-slot:prepend>
          <v-app-bar-nav-icon></v-app-bar-nav-icon>
        </template>

        <v-app-bar-title>Photos</v-app-bar-title>

        <nav>
          <v-btn>
            <RouterLink to="/">Home</RouterLink>
          </v-btn>
          <v-btn>
            <RouterLink to="/counter">Counter</RouterLink>
          </v-btn>
          <v-btn>
            <RouterLink to="/about">About</RouterLink>
          </v-btn>
        </nav>

        <template v-slot:append>
          <v-btn icon>
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>
      </v-app-bar>
    </v-layout>
  </v-card>
</template>

<style scoped></style>
