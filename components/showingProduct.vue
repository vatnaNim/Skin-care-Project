<template>
  <div class="w-[90%] mx-auto">
    <div class="my-12 flex gap-8 justify-center items-center">
      <button
        @click="filterType = 'Best-Seller'"
        :class="{
          'bg-[#459D7A] text-white px-12 py-2.5 rounded-md text-[16px] leading-[22px] hover:bg-green-600 duration-300':
            filterType === 'Best-Seller',
          'text-[#459D7A] px-12 py-2.5 rounded-md text-[16px] leading-[22px]':
            filterType !== 'Best-Seller',
        }"
      >
        Best-sellers
      </button>
      <button
        :class="{
          'bg-[#459D7A] text-white px-12 py-2.5 rounded-md text-[16px] leading-[22px] hover:bg-green-600 duration-300':
            filterType === 'New',
          'text-[#459D7A] px-12 py-2.5 rounded-md text-[16px] leading-[22px]':
            filterType !== 'New',
        }"
        @click="filterType = 'New'"
      >
        New product
      </button>
    </div>

    <div class="grid grid-cols-4 gap-4">
      <UiProductCard
        v-for="product in limitedProducts.slice(0, 4)"
        :key="product.id"
        :scrImage="product.scrImage"
        :productTitle="product.productTitle"
        :definition="product.definition"
        :price="product.price"
        :promotionPrice="product.promotionPrice"
        :shopLink="product.shopLink"
        :productTranding="product.productTranding"
        :details="product.details"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from "vue";
import { productData } from "~/contents/Data/productData";

const filterType = ref<string>("Best-Seller");

const limitedProducts = computed(() =>
  productData
    .filter((product) => product.productTranding === filterType.value)
    .slice(0, 4)
);
</script>
