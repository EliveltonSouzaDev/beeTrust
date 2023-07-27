<template>
  <div class="topbar"></div>
  <v-app class="max-width-app">
    <v-layout>
      <DefaultBar />
      <DefaultView
    /></v-layout>
  </v-app>
</template>

<script setup>
import DefaultBar from "./AppBar.vue";
import DefaultView from "./View.vue";
</script>

<style>
.max-width-app {
  max-width: 1400px;
  margin: 0 auto;
}

.teste {
  border: solid red 2px;
}

.topbar {
  position: fixed;
  width: 100%;
  height: 64px;
  background-color: #e9b857;
}
</style>
