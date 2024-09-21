<template>
  <div class="w-[70%] flex flex-col items-center">
    <span class="my-5 flex flex-col gap-8 text-center">
      <h1 class="text-4xl font-semibold">Thank you for your purchase!</h1>
      <p class="text-base text-[#9095A0]">
        You will receive an confirmation letter through your email
      </p></span
    >

    <div
      class="w-[80%] border-2 border-[#F3F4F6] rounded-md shadow-md p-6 my-8"
    >
      <div class="flex flex-col gap-3 border-b-2 pb-4">
        <div class="w-full flex items-center justify-between">
          <span class="flex gap-4">
            <img
              class="w-[24px] green-filter"
              :src="calenderIcon"
              alt="calender_icon"
            />

            <p class="text-[16px] leading-[26px] text-[#9095a0]">Date</p>
          </span>
          <p class="text-[16px] leading-[26px] text-black">18/09/2024</p>
        </div>

        <div class="w-full flex items-center justify-between">
          <span class="flex gap-4">
            <img
              class="w-[24px] green-filter"
              :src="personIcon"
              alt="Date_icon"
            />

            <p class="text-[16px] leading-[26px] text-[#9095a0]">Customer</p>
          </span>
          <p class="text-[16px] leading-[26px] text-black">Alvado Gaduate</p>
        </div>
        <div class="w-full flex items-center justify-between">
          <span class="flex gap-4">
            <img
              class="w-[24px] green-filter"
              :src="walletIcon"
              alt="wallat_icon"
            />

            <p class="text-[16px] leading-[26px] text-[#9095a0]">
              Payment Method
            </p>
          </span>
          <img
            class="w-10 overflow-hidden"
            :src="mastercardIcon"
            alt="master_l0go"
          />
        </div>
      </div>
      <div class="mt-5 gap-3 flex flex-col">
        <div class="w-full flex items-center justify-between">
          <span class="flex gap-4">
            <img
              class="w-[24px] green-filter"
              :src="resultIcon"
              alt="recept_icon"
            />

            <p class="text-[16px] leading-[26px] text-[#9095a0]">
              Order Number
            </p>
          </span>
          <p class="text-lg">123-456-789</p>
        </div>

        <div class="w-full flex items-center justify-between">
          <span class="flex gap-4">
            <img
              class="w-[24px] green-filter"
              :src="dollarIcon"
              alt="dollar_icon"
            />

            <p class="text-[16px] leading-[26px] text-[#9095a0]">Total</p>
          </span>
          <p class="text-2xl font-semibold">$187</p>
        </div>
      </div>

      <div>
        <h3 class="text-2xl font-bold my-4">Order Line</h3>

        <div
          v-for="(item, index) in productData.slice(0, 3)"
          :key="item.id"
          :productName="item.productTitle"
          :price="item.promotionPrice"
          :productScr="item.scrImage"
          class="border-t flex items-center justify-between py-4"
        >
          <div class="flex items-center gap-4">
            <img
              class="w-[101px] h-[127px] rounded-md"
              :src="item.scrImage"
              :alt="item.productTitle"
            />
            <article class="flex gap-2 flex-col">
              <h4 class="text-base font-semibold">{{ item.productTitle }}</h4>
              <p class="text-sm text-gray-400">Size: 50ml</p>
              <span class="py-0.5 px-2 bg-gray-300 text-center rounded-full"
                >x1 Items</span
              >
            </article>
          </div>

          <p class="font-bold text-md">${{ item.promotionPrice }}</p>
        </div>
      </div>
      <nuxt-link to="/shop/shopPage">
        <button
          class="px-8 rounded-md py-3.5 bg-[#459d7a] hover:bg-green-800 duration-300 text-white"
        >
          Continue shopping
        </button>
      </nuxt-link>
    </div>
  </div>
</template>

<script setup lang="ts">
import { productData } from "~/contents/Data/productData";
import {
  calenderIcon,
  personIcon,
  dollarIcon,
  walletIcon,
  resultIcon,
  mastercardIcon,
} from "~/public/Icons/icons";
</script>

<style scoped>
.green-filter {
  filter: invert(28%) sepia(55%) saturate(533%) hue-rotate(55deg)
    brightness(94%) contrast(98%);
}
</style>
