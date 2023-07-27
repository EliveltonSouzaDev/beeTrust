<template>
  <v-text-field
    :class="mdAndUp ? 'px-14' : 'px-1'"
    hide-details
    solo
    single-line
    light
    cleareble
    name="name"
    label="Search"
    bg-color="#FFFFFF"
    density="compact"
    prepend-inner-icon="mdi-magnify"
    id="searchField"
    variant="outlined"
  ></v-text-field>
</template>

<script setup>
import { useDisplay } from "vuetify";

const { mdAndUp } = useDisplay();
</script>
