<template>
  <v-btn class="mt-1 mr-3" id="btnWallet" @click="clicked">
    <template #append>
      <v-img :id="'myWallet'" height="40" width="40" :src="imgWallet" />
    </template>
    <span v-if="isLoggedIn"
      >Wallet Connected <v-icon icon="mdi-checkbox-marked-circle"></v-icon
    ></span>
    <span v-else>.Connect Wallet</span>
  </v-btn>
</template>

<script setup>
import { ref, onMounted } from "vue";
import imgWallet from "@/assets/metamask/metamask-icon.svg";

const isLoggedIn = ref(false);
const address = ref("");

onMounted(async () => {
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

//verifica se o usuário trocou de conta
window.ethereum.on("accountsChanged", handleAccountsChanged);

function handleAccountsChanged(accounts) {
  if (accounts.length === 0) {
    console.log("Please connect to MetaMask.");
    isLoggedIn.value = false;
  } else if (accounts[0] !== address.value) {
    address.value = accounts[0];
    isLoggedIn.value = true;
  }
}
</script>
