<template>
  <div class="w-[80%] flex flex-col gap-4 my-8">
    <div
      :class="[
        'w-full h-[305px] rounded-lg border shadow-md flex flex-row gap-5   ',
        // (index + 1) % 2 === 0 ? 'flex-row-reverse' : '',
      ]"
      class="even:flex-row-reverse"
      v-for="(value, index) in dataEvent"
      :key="index"
    >
      <div class="w-[50%]">
        <Nuxt-link :to="value.rountShop">
          <img
            class="w-full h-full rounded-md"
            :src="value.ImageScr"
            :alt="value.eventTitle"
          />
        </Nuxt-link>
      </div>

      <div class="w-[50%] flex justify-center items-start gap-4 flex-col px-12">
        <h2 class="text-xl font-semibold">{{ value.eventTitle }}</h2>
        <p class="text-[18px] leading-[28px]">{{ value.detail }}</p>
        <Nuxt-link :to="value.rountShop">
          <button
            class="mt-5 px-10 py-2 bg-[#459D7A] rounded-md text-[18px] leading-[28px] text-white hover:bg-green-800 duration-300"
          >
            {{ value.buttonName }}
          </button>
        </Nuxt-link>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import {
  evenScr,
  evenScr2,
  evenScr3,
  containerImage,
} from "~/assets/images/images";

interface iDataEvent {
  ImageScr: string;
  eventTitle: string;
  detail: string;
  rountShop: string;
  buttonName: string;
}
const dataEvent: iDataEvent[] = [
  {
    ImageScr: evenScr,
    eventTitle: "Promotion title",
    detail:
      "Et ipsum irure amet cupidatat mollit exercitation consequat duis aliquip. Reprehenderit Lorem veniam pariatur esse pariatur in aute tempor au",
    rountShop: "/shop/shopPage",
    buttonName: "Shop Now",
  },
  {
    ImageScr: evenScr2,
    eventTitle: "Promotion title",
    detail:
      "Et ipsum irure amet cupidatat mollit exercitation consequat duis aliquip. Reprehenderit Lorem veniam pariatur esse pariatur in aute tempor au",
    rountShop: "/shop/shopPage",
    buttonName: "Shop Now",
  },
  {
    ImageScr: evenScr3,
    eventTitle: "Gift for your skin",
    detail:
      "Enim officia magna ut esse aliquip irure consectetur dolor dolor commodo et. Cupid",
    rountShop: "/shop/shopPage",
    buttonName: "Shop Now",
  },
  {
    ImageScr: containerImage,
    eventTitle: "Gift for your skin",
    detail:
      "Enim officia magna ut esse aliquip irure consectetur dolor dolor commodo et. Cupid",
    rountShop: "/shop/shopPage",
    buttonName: "Shop Now",
  },
];
</script>

<style scoped></style>
