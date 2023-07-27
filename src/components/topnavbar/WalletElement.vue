<template>
  <v-btn class="mt-1 mr-3" id="btnWallet" @click="clicked">
    <template #append>
      <v-img :id="'myWallet'" height="40" width="40" :src="imgWallet" />
    </template>
    <span>.Connect Wallet</span>
  </v-btn>
</template>

<script setup>
import imgWallet from "@/assets/metamask/metamask-icon.svg";
</script>
