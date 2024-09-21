<template>
  <div class="border border-[#F3F4F6] rounded-md shadow-md px-8 py-5">
    <span class="flex items-center gap-3 mb-5">
      <img :src="circleUser" alt="circile_icon" />
      <h2 class="text-2xl font-semibold">Customer Information</h2>
    </span>

    <div class="space-y-6">
      <div class="flex items-center space-x-8">
        <div>
          <label class="text-gray-600 text-sm font-bold">Full name</label>
          <input
            type="text"
            value="Amaya Dunn"
            class="block w-full mt-1 text-base bg-[#F3f4f6] rounded-md px-4 py-2 focus:ring-0 focus:outline-none"
          />
        </div>
        <div>
          <label class="text-gray-600 text-sm font-bold">Phone number</label>
          <input
            type="text"
            value="732-123-4567"
            class="block w-full mt-1 rounded-md px-4 py-2 bg-[#F3f4f6] text-base focus:ring-0 focus:outline-none"
          />
        </div>
      </div>
      <div>
        <label class="text-gray-600 text-sm font-bold">Address</label>
        <input
          type="text"
          value="4798 Pool Street, Bayville, New Jersey(NJ)"
          class="block w-full mt-1 rounded-md px-4 py-2 bg-[#F3f4f6] text-base focus:ring-0 focus:outline-none"
        />
      </div>
      <div class="flex items-center space-x-4">
        <input
          type="checkbox"
          class="form-checkbox scale-125 accent-[#459d7a]"
          checked
        />
        <label>Save as default</label>
      </div>
      <div class="text-sm">
        <span
          class="flex items-center space-x-3 border-[#905f4b] bg-stone-100 border p-4 rounded-md"
        >
          <img :src="infoIcon" alt="infoIcon" />
          <span
            ><h3 class="font-bold">Delivery note</h3>
            Billing and address name must match the provider’s records
          </span>
        </span>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { circleUser, infoIcon } from "~/public/Icons/icons";
</script>

<style scoped></style>
