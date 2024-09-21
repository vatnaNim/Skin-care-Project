<template>
  <div class="rounded-lg shadow-[5px_3px_3px_rgba(0,0,0,0.3)]">
    <div class="overflow-hidden relative">
      <nuxt-link :to="propsItem.shopLink">
        <img
          class="object-cover rounded-xl filter brightness-100 hover:scale-105 translate-all ease-in-out duration-300 overflow-hidden"
          :src="propsItem.scrImage"
          :alt="propsItem.productTitle"
        />
        <span
          class="bg-[#FFC970] text-[#774900] rounded-md absolute top-5 right-5"
          >{{ propsItem.productTranding }}</span
        >
      </nuxt-link>
    </div>

    <div class="text-[14px] leading-[48px] p-4">
      <h4 class="font-semibold">
        {{ propsItem.productTitle }}
      </h4>
      <p>{{ propsItem.definition }}</p>
      <div class="flex justify-between items-center">
        <div class="flex items-center gap-2">
          <h3 class="font-bold text-2xl">${{ propsItem.promotionPrice }}</h3>
          <h5 class="text-[16px] text-[#9095A0] leading-[26px] line-through">
            ${{ propsItem.price }}
          </h5>
        </div>
        <nuxt-link :to="propsItem.shopLink">
          <button
            class="border-[#459D7A] border-2 p-3 rounded-full hover:bg-[#bbbcc0] duration-300"
          >
            <svg
              class="text-[#459D7A] fill-current"
              xmlns="http://www.w3.org/2000/svg"
              height="24px"
              viewBox="0 -960 960 960"
              width="24px"
              fill="#5f6368"
            >
              <path
                d="M280-80q-33 0-56.5-23.5T200-160q0-33 23.5-56.5T280-240q33 0 56.5 23.5T360-160q0 33-23.5 56.5T280-80Zm400 0q-33 0-56.5-23.5T600-160q0-33 23.5-56.5T680-240q33 0 56.5 23.5T760-160q0 33-23.5 56.5T680-80ZM246-720l96 200h280l110-200H246Zm-38-80h590q23 0 35 20.5t1 41.5L692-482q-11 20-29.5 31T622-440H324l-44 80h480v80H280q-45 0-68-39.5t-2-78.5l54-98-144-304H40v-80h130l38 80Zm134 280h280-280Z"
              />
            </svg></button
        ></nuxt-link>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
const propsItem = defineProps({
  scrImage: {
    type: String,
    required: true,
  },
  productTitle: {
    type: String,
    required: true,
  },
  definition: {
    type: String,
    required: true,
  },
  price: {
    type: Number,
    required: true,
  },
  promotionPrice: {
    type: Number,
    required: true,
  },
  shopLink: {
    type: String,
    required: true,
  },
  productTranding: {
    type: String,
    required: true,
  },
});
</script>
