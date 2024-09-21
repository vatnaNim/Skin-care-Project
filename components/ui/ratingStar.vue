<template>
  <div>
    <div class="flex items-center">
      <div
        v-for="(star, index) in stars"
        :key="index"
        @click="selectRating(index + 1)"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="currentColor"
          viewBox="0 0 24 24"
          stroke="currentColor"
          class="w-[24px] h-[24px] cursor-pointer"
          :class="index < selectedRating ? 'text-[#F3C63F]' : 'text-[#DEE1E6]'"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M12 17.27l5.18 3.73-1.64-6.88L20 8.24l-7.19-.61L12 2 11.19 7.63 4 8.24l5.46 5.88-1.64 6.88z"
          />
        </svg>
      </div>
      <span class="ml-3 text-[16px] leading-[26px] font-bold">{{
        selectedRating
      }}</span>
    </div>
  </div>
</template>

<script setup lang="ts">
const stars = Array(5).fill(4);
const selectedRating = ref(4);

const selectRating = (rating: number) => {
  selectedRating.value = rating;
};
</script>

<style scoped></style>
