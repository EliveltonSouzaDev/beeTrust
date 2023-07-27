<template>
  <section class="d-flex flex-column h-100">
    <ProductCard :products="products" @onClickProduct="handleClickProduct" />
  </section>
</template>

<script setup>
import ProductCard from "@/components/ProductCard.vue";
import { ref } from "vue";
import { useRouter } from "vue-router";
const router = useRouter();

const products = ref([
  {
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
  },
  {
    title: "Onix Plus TZTurbo 2020",
    text: "Whitehaven Beach Adipisicing excepteur irure mollit dolore do. Eiusmod id deserunt commodo consequat minim magna ea laborum commodo aliqua cillum. Pariatur ea esse eu consequat sint pariatur ipsum mollit estlabore.",
    src: [
      "https://img.freepik.com/fotos-gratis/um-estacionamento-de-jipe-azul-na-zona-publica_114579-4042.jpg?w=1380&t=st=1690075957~exp=1690076557~hmac=c8007429c16ba100a1bf93a0d606767ccca797c8de99fb482ef05e9fbfcf541d",
      "https://img.freepik.com/fotos-gratis/vista-frontal-de-um-sedan-de-luxo-preto-na-estrada_114579-5030.jpg?w=1380&t=st=1690083069~exp=1690083669~hmac=6857555c710bea73026046f2032ca1fca355c7e7190aa01b5badd044e26d6f14",
      "https://img.freepik.com/fotos-gratis/movimentacao-preta-da-estrada-do-carro-desportivo-no-por-do-sol_114579-5064.jpg?w=1380&t=st=1690076011~exp=1690076611~hmac=2071dceeeed47c1617950f284c143158b56052b9939ed8d2a3449d5a160637f3",
      "https://img.freepik.com/fotos-gratis/um-cupe-mini-vermelho-dirigindo-na-estrada-com-alta-velocidade_114579-4060.jpg?w=1380&t=st=1689696492~exp=1689697092~hmac=4439fa392587902ba125df4412aeaaba4a266f3be8eb1f4fa8ef8e1bf9d59f65",
    ],
    closing: "14d 22h 30min",
    posted: "03/02/2023 19:20",
    price: "$300.000",
    collateral: "0.05555",
  },
  {
    title: "Fiat Mobi Like 1.0 Fire Flex 5 portas",
    text: "Whitehaven Beach Adipisicing excepteur irure mollit dolore do. Eiusmod id deserunt commodo consequat minim magna ea laborum commodo aliqua cillum. Pariatur ea esse eu consequat sint pariatur ipsum mollit estlabore.",
    src: [
      "https://img.freepik.com/fotos-gratis/movimentacao-preta-da-estrada-do-carro-desportivo-no-por-do-sol_114579-5064.jpg?w=1380&t=st=1690076011~exp=1690076611~hmac=2071dceeeed47c1617950f284c143158b56052b9939ed8d2a3449d5a160637f3",
      "https://img.freepik.com/fotos-gratis/um-cupe-mini-vermelho-dirigindo-na-estrada-com-alta-velocidade_114579-4060.jpg?w=1380&t=st=1689696492~exp=1689697092~hmac=4439fa392587902ba125df4412aeaaba4a266f3be8eb1f4fa8ef8e1bf9d59f65",
      "https://img.freepik.com/fotos-gratis/um-estacionamento-de-jipe-azul-na-zona-publica_114579-4042.jpg?w=1380&t=st=1690075957~exp=1690076557~hmac=c8007429c16ba100a1bf93a0d606767ccca797c8de99fb482ef05e9fbfcf541d",
      "https://img.freepik.com/fotos-gratis/vista-frontal-de-um-sedan-de-luxo-preto-na-estrada_114579-5030.jpg?w=1380&t=st=1690083069~exp=1690083669~hmac=6857555c710bea73026046f2032ca1fca355c7e7190aa01b5badd044e26d6f14",
    ],
    closing: "14d 22h 30min",
    posted: "03/02/2023 19:20",
    price: "$300.000",
    collateral: "0.05555",
  },
  {
    title: "Onix Plus TZTurbo 2020",
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
  },
  {
    title: "Fiat Like 1.0 Fire Flex 5 portas",
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
  },
  {
    title: "Onix TZTurbo 2020",
    text: "Whitehaven Beach Adipisicing excepteur irure mollit dolore do. Eiusmod id deserunt commodo consequat minim magna ea laborum commodo aliqua cillum. Pariatur ea esse eu consequat sint pariatur ipsum mollit estlabore.",
    src: [
      "https://img.freepik.com/fotos-gratis/um-estacionamento-de-jipe-azul-na-zona-publica_114579-4042.jpg?w=1380&t=st=1690075957~exp=1690076557~hmac=c8007429c16ba100a1bf93a0d606767ccca797c8de99fb482ef05e9fbfcf541d",
      "https://img.freepik.com/fotos-gratis/um-cupe-mini-vermelho-dirigindo-na-estrada-com-alta-velocidade_114579-4060.jpg?w=1380&t=st=1689696492~exp=1689697092~hmac=4439fa392587902ba125df4412aeaaba4a266f3be8eb1f4fa8ef8e1bf9d59f65",
      "https://img.freepik.com/fotos-gratis/vista-frontal-de-um-sedan-de-luxo-preto-na-estrada_114579-5030.jpg?w=1380&t=st=1690083069~exp=1690083669~hmac=6857555c710bea73026046f2032ca1fca355c7e7190aa01b5badd044e26d6f14",
      "https://img.freepik.com/fotos-gratis/movimentacao-preta-da-estrada-do-carro-desportivo-no-por-do-sol_114579-5064.jpg?w=1380&t=st=1690076011~exp=1690076611~hmac=2071dceeeed47c1617950f284c143158b56052b9939ed8d2a3449d5a160637f3",
    ],
    closing: "14d 22h 30min",
    posted: "03/02/2023 19:20",
    price: "$300.000",
    collateral: "0.05555",
  },
  {
    title: "Fiat Mobi Like 1.0 Fire",
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
  },
  {
    title: "Onix Plus 2020",
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
  },
  {
    title: "Onix TZTurbo 2020",
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
  },
  {
    title: "Onix Plus TZTurbo 2020",
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
  },
  {
    title: "Onix Plus TZTurbo 2020",
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
  },
  {
    title: "Onix Plus TZTurbo 2020",
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
  },
  {
    title: "Onix Plus TZTurbo 2020",
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
  },
  {
    title: "Onix Plus TZTurbo 2020",
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
  },
]);

const handleClickProduct = (item) => {
  router.push({ name: "Product", params: { id: 1 } });
};
</script>

<style scoped></style>
