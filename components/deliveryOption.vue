<template>
  <div class="w-full border border-[#F3F4F6] rounded-md shadow-md p-8">
    <span class="flex gap-3"
      ><img :src="localShipping" alt="icon_delivery" />
      <h3 class="text-2xl font-semibold">Delivery Options</h3></span
    >
    <h4 class="font-medium text-lg mb-1 text-[#424955] my-5">Operator</h4>
    <div class="flex items-center text-lg space-x-6">
      <label class="flex items-center space-x-2">
        <input
          type="radio"
          name="delivery"
          class="form-radio accent-green-700 scale-150"
          checked
        />
        <span>UPS</span>
      </label>
      <label class="flex items-center space-x-2">
        <input
          type="radio"
          name="delivery"
          class="form-radio accent-green-700 scale-150"
        />
        <span>FedEx</span>
      </label>
      <label class="flex items-center space-x-2">
        <input
          type="radio"
          name="delivery"
          class="form-radio accent-green-700 scale-150"
        />
        <span>DHL</span>
      </label>
    </div>

    <div class="grid grid-cols-2 gap-4 my-4">
      <div
        :class="[
          'flex items-center space-x-4 border-2 p-4 rounded-lg cursor-pointer',
          selectedOption === 'instant'
            ? 'bg-green-100 border-[#459D7A] text-green-800'
            : 'border-gray-300',
        ]"
        @click="selectOption('instant')"
      >
        <img :src="checkCircleIcon" alt="checkIcon" />
        <div class="flex flex-col">
          <span class="text-[#459D7A] font-bold text-xl">$22</span>
          <span class="text-base">
            Instant delivery<br />Est. arrival: Today
          </span>
        </div>
      </div>

      <div
        :class="[
          'flex items-center space-x-4 border-2 p-4 rounded-lg cursor-pointer',
          selectedOption === 'standard'
            ? 'bg-green-100 border-[#459D7A] text-green-800'
            : 'border-gray-300',
        ]"
        @click="selectOption('standard')"
      >
        <img :src="checkCircleIcon" alt="checkIcon" />
        <div class="flex flex-col">
          <span class="text-[#459D7A] font-bold text-xl">$12</span>
          <span class="text-base">
            Standard delivery<br />Est. arrival: 09/18
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { localShipping, checkCircleIcon } from "~/public/Icons/icons";
import { ref } from "vue";

const selectedOption = ref("");
const selectOption = (option: string) => {
  selectedOption.value = option;
};
</script>

<style scoped></style>
