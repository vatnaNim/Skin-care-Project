<template>
  <div class="w-full my-4">
    <h1 class="text-[40px] leading-[48px] font-semibold my-12">
      Related products
    </h1>
    <div class="grid grid-cols-4 gap-8">
      <UiProductCard
        v-for="(product, index) in productData.slice(0, 4)"
        :key="product.id"
        :scrImage="product.scrImage"
        :productTitle="product.productTitle"
        :definition="product.definition"
        :price="product.price"
        :promotionPrice="product.promotionPrice"
        :shopLink="product.shopLink"
        :productTranding="product.productTranding"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { productData } from "~/contents/Data/productData";
</script>
