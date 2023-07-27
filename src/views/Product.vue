<template>
  <div
    class="d-flex flex-column justify-space-around px-4 mx-auto"
    :class="mdAndUp ? 'w-75' : 'w-100'"
    :style="mdAndUp ? 'max-height: calc(100vh - 100px)' : 'height:90%'"
  >
    <section class="d-flex align-end justify-space-between w-100">
      <div class="my-4 align-self-start">
        <v-btn
          variant="outlined"
          class="w-20 align-self-start pl-4 mt-2"
          color="blue-darken-1"
          @click="$router.push({ name: 'Home' })"
        >
          <v-icon start icon="mdi-arrow-left"></v-icon>
          Back
        </v-btn>
      </div>
    </section>

    <section class="d-flex align-end justify-space-between w-100">
      <h2 class="align-self-end">{{ product.title }}</h2>
      <div v-if="mdAndUp" class="mt-4 align-self-end">
        <v-btn
          min-width="150px"
          class="align-self-end pl-4 mt-2"
          color="blue-darken-1"
          @click="$router.push({ name: 'Home' })"
        >
          <v-icon start icon="mdi-handshake"></v-icon>
          Deal
        </v-btn>
      </div>
    </section>

    <v-carousel
      class="py-md-4"
      :height="mdAndUp ? 'auto' : '250'"
      :continuous="false"
      hide-delimiter-background
      color="#ffff"
    >
      <v-carousel-item
        v-for="(item, i) in product.src"
        :key="i"
        :src="item"
        :contain="!mdAndUp ? true : false"
        :cover="mdAndUp ? true : false"
      ></v-carousel-item>
    </v-carousel>
    <section class="d-flex flex-column pt-md-4">
      <p>{{ product.text }}</p>
      <div class="d-flex justify-space-between justify-self-end mt-3 w-100">
        <p class="text-caption text-light-blue-darken-3">
          Closing in {{ product.closing }}
        </p>
        <p cols="12" class="text-caption text-grey-lighten-1">
          posted {{ product.posted }}
        </p>
      </div>
      <div class="d-flex justify-space-between justify-self-end pt-2 w-100">
        <p class="font-weight-bold text-h6">{{ product.price }}</p>
        <p cols="12" class="font-weight-bold text-subtitle-2">
          Colateral ETH
          <span class="text-blue-darken-1 text-subtitle-1 font-weight-bold">{{
            product.collateral
          }}</span>
        </p>
      </div>
    </section>

    <div v-if="smAndDown" class="align-self-center w-75">
      <v-btn
        size="large"
        class="w-100 align-self-center pl-4"
        color="blue-darken-1"
        @click="$router.push({ name: 'Home' })"
      >
        <v-icon start icon="mdi-handshake"></v-icon>
        Deal
      </v-btn>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useDisplay } from "vuetify";

const { mdAndUp, smAndDown } = useDisplay();

const product = ref({
  title: "Fiat Mobi Like 1.0 Fire Flex 5 portas",
  text: "Whitehaven Beach Adipisicing excepteur irure mollit dolore do. Eiusmod id deserunt commodo consequat minim magna ea laborum commodo aliqua cillum. Pariatur ea esse eu consequat sint pariatur ipsum mollit estlabore.",
  src: [
    "https://img.freepik.com/fotos-gratis/um-cupe-mini-vermelho-dirigindo-na-estrada-com-alta-velocidade_114579-4060.jpg?w=1380&t=st=1689696492~exp=1689697092~hmac=4439fa392587902ba125df4412aeaaba4a266f3be8eb1f4fa8ef8e1bf9d59f65",
    "https://img.freepik.com/fotos-gratis/um-estacionamento-de-jipe-azul-na-zona-publica_114579-4042.jpg?w=1380&t=st=1690075957~exp=1690076557~hmac=c8007429c16ba100a1bf93a0d606767ccca797c8de99fb482ef05e9fbfcf541d",
    "https://img.freepik.com/fotos-gratis/vista-frontal-de-um-sedan-de-luxo-preto-na-estrada_114579-5030.jpg?w=1380&t=st=1690083069~exp=1690083669~hmac=6857555c710bea73026046f2032ca1fca355c7e7190aa01b5badd044e26d6f14",
    "https://img.freepik.com/fotos-gratis/movimentacao-preta-da-estrada-do-carro-desportivo-no-por-do-sol_114579-5064.jpg?w=1380&t=st=1690076011~exp=1690076611~hmac=2071dceeeed47c1617950f284c143158b56052b9939ed8d2a3449d5a160637f3",
  ],
  closing: "14d 22h 30min",
  posted: "03/02/2023 19:20",
  price: "$300.000",
  collateral: "0.05555",
});
</script>

<style scoped>
.teste {
  border: 2px solid red;
}
</style>
