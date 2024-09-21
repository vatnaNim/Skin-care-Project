<template>
  <div
    class="flex flex-col gap-3.5 overflow-hidden rounded-[8px] shadow-[3px_4px_4px_0px_#00000040]"
    v-for="(card, index) in ingredientsCards"
  >
    <img class="w-full h-[216px]" :src="card.cardScr" alt="" />
    <h2 class="text-[20px] leading-[26px] font-semibold px-4">
      {{ card.cardName }}
    </h2>
    <p class="text-[16px] leading-[26px] text-[#323842] line-clamp-3 px-4 mb-4">
      {{ card.cardDetail }}
    </p>
  </div>
</template>

<script setup lang="ts">
import { greenTea, hyaluronicAcid, oliveOil } from "@/static/productScr";
const ingredientsCards = [
  {
    cardId: 1,
    cardScr: hyaluronicAcid,
    cardName: "Hyaluronic acid",
    cardDetail:
      "Elit do sit excepteur duis labore nisi sit anim adipisicing duis incididunt sit anim sint est exercitation aute consectetur irure",
  },
  {
    cardId: 2,
    cardScr: greenTea,
    cardName: "Green tea",
    cardDetail:
      "Tempor adipisicing aute pariatur magna enim Lorem voluptate incididunt culpa ex veniam sunt occaecat tempor ",
  },
  {
    cardId: 3,
    cardScr: oliveOil,
    cardName: "Olive oil",
    cardDetail:
      "Cupidatat culpa id do laboris nisi aliqua eu. Veniam aliqua duis Lorem adipisicing et minim velit quis ",
  },
];
</script>
