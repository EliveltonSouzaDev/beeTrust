<template>
  <v-app-bar app color="#e9b857" flat d-flex :extended="xs">
    <v-container class="d-flex justify-space-around px-0">
      <LogoElement @drawerChangeStatus="changeDrawer()" />
      <SearchElement :class="xs ? 'hidden-xs' : ''" />
      <WalletElement @click="$router.push({ name: 'Login' })" />
    </v-container>
    <template v-slot:extension v-if="xs">
      <SearchElement class="px-5 mb-5" />
    </template>
  </v-app-bar>
  <v-navigation-drawer app v-model="drawer">
    <v-list
      :class="xs ? 'font-weight-medium pa-0 ma-0' : 'pt-5 font-weight-medium'"
    >
      <v-list-item class="how-work-item">.How does it work? </v-list-item>
      <v-dialog v-model="dialog" activator="parent" width="600px">
        <v-card>
          <v-card-text class="d-flex flex-column text-subtitle-2">
            <span>
              A trading platform with the premise of using the Metamask wallet
              for cryptocurrencies works as an online environment where users
              can buy, sell, and exchange digital assets, especially
              cryptocurrencies, in a decentralized manner. Metamask is used as
              the primary digital wallet, allowing users to securely store and
              manage their cryptocurrency assets
            </span>
            <span class="my-4"
              >When registering on the platform, users connect their Metamask
              wallet through a browser extension or web application. With the
              wallet linked, they can access their cryptocurrencies and assets
              on the Ethereum blockchain and interact with the various features
              offered by the platform.</span
            >
            <span>
              Users can explore available trading options, such as different
              cryptocurrency pairs or tokens, and execute transactions directly
              from their Metamask wallets. This ensures that the assets remain
              under the user's control at all times, as transactions are signed
              and authorized by the wallet, without the need to transfer funds
              to the platform's custody.
            </span>
          </v-card-text>
          <v-card-actions>
            <v-btn color="blue-darken-1" block @click="dialog = false"
              >OK</v-btn
            >
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-list>
    <v-list
      class="new-item-list"
      :class="
        xs
          ? 'font-weight-bold teal-darken-4 pa-0 ma-0'
          : 'pt-5 font-weight-bold teal-darken-4'
      "
    >
      <v-list-item>+ List an Item</v-list-item>
    </v-list>
    <v-list
      class="category-item"
      compact
      :class="xs ? 'font-weight-regular pa-0 ma-0' : 'pt-5 font-weight-regular'"
    >
      <v-list-item class="font-weight-bold">CATEGORIES</v-list-item>
      <v-list-item @click="$router.push({ name: 'Home' })"
        >.all categories</v-list-item
      >
      <v-list-item v-for="category in categories" :key="category">{{
        category
      }}</v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script setup>
import LogoElement from "@/components/topnavbar/LogoElement.vue";
import SearchElement from "@/components/topnavbar/SearchElement.vue";
import WalletElement from "@/components/topnavbar/WalletElement.vue";
import { ref } from "vue";
import { useDisplay } from "vuetify";

const { xs } = useDisplay();

const drawer = ref();
const dialog = ref(false);
const categories = ref([
  ".service & solution",
  ".travel & accommodation",
  ".real state & furniture",
  ".furniture & appliances",
  ".fashion & beauty",
  ".eletronic & media",
  ".food & personal care",
  ".toys, diy & hobbies",
  ".games & digital contents",
]);

function changeDrawer() {
  drawer.value = !drawer.value;
}
</script>

<style scoped lang="scss">
.category-item,
.new-item-list,
.how-work-item {
  cursor: pointer;
}
</style>
