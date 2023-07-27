<template>
  <v-virtual-scroll :items="productsSpliced" :item-height="50" height="300">
    <template v-slot:default="{ item, index }">
      <section
        @click="$emit('onClickProduct', item)"
        class="d-flex align-start ml-2 pr-2 my-2 product-card"
      >
        <div class="d-flex" style="width: 30%">
          <img style="width: 100%" :src="item.src[0]" />
          <div
            class="d-flex align-center justify-center rounded-ts-sm py-1 rounded-be-sm picture-count"
          >
            <v-icon size="14" color="#ffff" icon="mdi-camera-outline"></v-icon>
            <span
              v-if="item.src.length > 1"
              class="pl-1 text-caption text-white"
            >
              {{ item.src.length }}</span
            >
          </div>
        </div>
        <div class="d-flex flex-column pa-2 card-content">
          <p class="pl-1 font-weight-black">{{ item.title }}</p>
          <v-card-text class="py-2 px-1 textLimit3">
            {{ item.text }}
          </v-card-text>
          <div class="d-flex justify-space-between justify-self-end pt-2">
            <p class="font-weight-bold text-subtitle-2">{{ item.price }}</p>
            <p cols="12" class="font-weight-bold text-subtitle-2">
              Colateral ETH
              <span
                class="text-blue-darken-1 text-subtitle-2 font-weight-bold"
                >{{ item.collateral }}</span
              >
            </p>
          </div>
          <div class="d-flex justify-space-between justify-self-end mt-3">
            <p class="text-caption text-light-blue-darken-3">
              Closing in {{ item.closing }}
            </p>
            <p cols="12" class="text-caption text-grey-lighten-1">
              posted {{ item.posted }}
            </p>
          </div>
        </div>
      </section>
      <div class="d-flex justify-md-end justify-center">
        <v-pagination
          v-if="productsSpliced.length - 1 === index"
          v-model="page"
          :length="numPages"
          density="comfortable"
          size="small"
          rounded="circle"
          activeColor="primary"
          :total-visible="7"
        ></v-pagination>
      </div>
    </template>
  </v-virtual-scroll>
</template>
<script setup>
import { ref, computed } from "vue";

const props = defineProps({
  products: {
    type: Array,
    required: true,
  },
});

const page = ref(1);
const pageSize = ref(10);

const numPages = computed(() => {
  return Math.ceil(props.products.length / pageSize.value);
});

const productsSpliced = computed(() => {
  const startIndex = (page.value - 1) * pageSize.value;

  const data = [...props.products];

  return data.splice(startIndex, pageSize.value);
});
</script>
<style lang="scss" scoped>
.card-content {
  width: 70%;
  min-height: 180px;
}
.picture-count {
  width: 32px;
  height: 20px;
  background-color: #4a4a4a;
  position: absolute;
  opacity: 0.9;
}

.product-card {
  background-color: #f9f9f9;
  cursor: pointer;
  border: 1px solid #e5e5e5;
  max-height: 180px;
  border-radius: 8px;
}
.product-card:hover {
  -webkit-box-shadow: 10px 9px 5px -6px rgba(97, 97, 97, 0.3);
  -moz-box-shadow: 10px 9px 5px -6px rgba(97, 97, 97, 0.3);
  box-shadow: 10px 9px 5px -6px rgba(97, 97, 97, 0.3);
}

img {
  max-height: 180px;
  border-top-left-radius: 8px;
  border-bottom-left-radius: 8px;
  object-fit: cover;
}
@media screen and (max-width: 900px) {
  .picture-count {
    visibility: hidden;
  }
  .card-content {
    max-height: 150px;
  }
  .product-card {
    height: 176px;
    max-width: 96%;
  }
  img {
    height: 176px;
  }
}
</style>
