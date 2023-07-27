<template>
  <section class="h-100 d-flex justify-center align-start mt-5">
    <div
      v-if="!isLoggedIn"
      class="d-flex align-center justify-center flex-column"
    >
      <v-img class="my-4" width="200" :src="imgWallet" />
      <v-btn
        v-if="isMetamaskSupported"
        color="blue-darken-1"
        @click="connectWallet"
      >
        Connect wallet
      </v-btn>
      <h2 v-else>Install Metamask extension</h2>
    </div>
    <div v-else class="d-flex flex-column align-center justify-center mt-5">
      <h1 class="text-h6 font-weight-bold mr-2">Connected with wallet</h1>
      <v-avatar color="info" class="my-4">
        <v-icon icon="mdi-account-circle"></v-icon>
      </v-avatar>
      <p class="text-subtitle-1 font-weight-bold">{{ computedAddress }}</p>
    </div>
  </section>
</template>
<script setup>
import { ref, onMounted, computed } from "vue";
import imgWallet from "@/assets/metamask/metamask-seeklogo.svg";

const isMetamaskSupported = ref(false);
const isLoggedIn = ref(false);
const address = ref("");

onMounted(async () => {
  isMetamaskSupported.value = (await window.ethereum) !== undefined;
  await isConnected();
});
//verifica se o usuário está conectado
async function isConnected() {
  const accounts = await ethereum.request({ method: "eth_accounts" });
  if (accounts.length) {
    isLoggedIn.value = true;
    address.value = accounts[0];
  } else {
    isLoggedIn.value = false;
    console.log("Metamask is not connected");
  }
}
//conecta o usuário ao clicar no botão
async function connectWallet() {
  try {
    const accounts = await window.ethereum.request({
      method: "eth_requestAccounts",
    });
    address.value = accounts[0];
    isLoggedIn.value = true;
  } catch (error) {
    isLoggedIn.value = false;
    console.error(error);
  }
}

const computedAddress = computed(() => {
  return address.value.substring(0, 6) + "...";
});

//verifica se o usuário trocou de conta
window.ethereum.on("accountsChanged", handleAccountsChanged);

function handleAccountsChanged(accounts) {
  if (accounts.length === 0) {
    console.log("Please connect to MetaMask.");
    isLoggedIn.value = false;
  } else if (accounts[0] !== address.value) {
    address.value = accounts[0];
  }
}
</script>
<style lang=""></style>
