<template>
  <v-btn
    class="hidden-md-and-down mt-1 ml-3"
    id="btnLogo"
    @click="$router.push({ name: 'Home' })"
  >
    <template #prepend>
      <v-img :id="'imgLogo'" height="40" width="40" :src="imgLogo" />
    </template>
    <span>.Bee Trust</span>
  </v-btn>
  <v-app-bar-nav-icon
    @click.stop="$emit('drawerChangeStatus')"
    :class="xs ? 'hidden-lg-and-up mb-3 ml-3' : 'hidden-lg-and-up mx-5'"
    icon="mdi-menu"
  ></v-app-bar-nav-icon>
</template>

<script setup>
import { useDisplay } from "vuetify";
import imgLogo from "@/assets/logo/beetrust_logo.svg";

const { xs } = useDisplay();
</script>
