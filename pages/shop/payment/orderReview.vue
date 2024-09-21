<template>
  <div class="w-[80%]">
    <h1 class="text-center text-3xl font-semibold my-12">
      My Shopping Bag (3)
    </h1>

    <div class="grid grid-cols-[65%_35%] mt-12 gap-4">
      <div class="w-full flex flex-col gap-4">
        <div class="border border-[#F3F4F6] rounded-md shadow-md p-4">
          <span class="flex gap-3"
            ><img :src="shoppingCart" alt="shopping_icon" />
            <h2 class="font-semibold text-2xl">Order Summary</h2></span
          >

          <div class="flex justify-between items-center px-4 py-5">
            <div class="w-1/4">
              <h2 class="text-sm text-[#565e6c] font-semibold">Name</h2>
            </div>

            <span class="text-sm text-[#565e6c] font-semibold">Text</span>
            <span class="text-sm text-[#565e6c] font-semibold"> Quantity</span>
            <span class="text-sm text-[#565e6c] font-semibold">Total</span>
            <button>
              <img :src="restartIcon" alt="icon_delete" class="w-6 h-6" />
            </button>
          </div>

          <div
            v-for="(item, index) in productData.slice(0, 3)"
            :key="item.id"
            :productTitle="item.productTitle"
            :promotionPricr="item.promotionPrice"
            :scrImg="item.scrImage"
            class="flex justify-between items-center border-b px-4 py-4"
          >
            <div class="w-1/4 flex items-center space-x-7">
              <img
                :src="item.scrImage"
                :alt="item.productTitle"
                class="w-[65px] h-[77px] rounded"
              />
              <div>
                <h3 class="font-bold text-sm text-[#424955]">Product name</h3>
                <select
                  class="border-2 border-gray-300 rounded px-8 py-1 text-sm text-gray-400 mt-0.5"
                >
                  <option class="text-black font-semibold bg-gray-100">
                    Size: 50ml
                  </option>
                  <option class="text-black font-semibold bg-gray-100">
                    Size: 60ml
                  </option>
                  <option class="text-black font-semibold bg-gray-100">
                    Size: 70ml
                  </option>
                  <option class="text-black font-semibold bg-gray-100">
                    Size: 80ml
                  </option>
                </select>
              </div>
            </div>

            <span class="text-base">${{ item.promotionPrice }}</span>
            <span class="flex text-sm space-x-1"
              ><img :src="editIcon" alt="edit_icon" />
              <p>2</p></span
            >
            <span class="text-[#459D7A] font-semibold">$ 84</span>
            <button>
              <img :src="deleteIcon" alt="icon_delete" class="w-6 h-6" />
            </button>
          </div>
        </div>
        <DeliveryOption />
        <CustomerForm />
      </div>

      <div>
        <div
          class="w-[352px] border-2 flex flex-col px-6 py-8 border-[#459D7A] rounded-md"
        >
          <h2 class="text-2xl font-semibold my-4">Payment Method</h2>
          <span class="text-sm text-[#379AE6] mb-1"
            >Change payment methods</span
          >
          <button
            class="flex justify-between items-center border-2 px-2.5 py-2 rounded-md border-[#459D7A] text-[#459D7A] bg-green-100"
          >
            <div class="flex gap-2 items-center">
              <img class="w-[35px] h-[36px]" :src="mastercardIcon" alt="" />
              <span class="">Mastercard</span>
            </div>
            <span>**** 5887</span>
          </button>

          <div class="flex gap-2 mt-12 mb-2">
            <div class="w-[216px] px-4 py-2 border border-[#459D7A] rounded-md">
              %15 OFF
            </div>
            <button
              class="px-4 py-2 text-[#459D7A] text-sm rounded-md bg-gray-100 hover:bg-green-100 duration-300"
            >
              Apply
            </button>
          </div>
          <span
            class="bg-[#FFC970] w-[50px] rounded-full py-1.5 px-2 text-center text-[#774900] text-nowrap text-[11px] leading-[18px]"
            >%15 off</span
          >

          <div class="flex flex-col gap-4 py-8">
            <img
              class="w-[24px] fill-current text-green-500"
              :src="resultIcon"
              alt="result_icon"
            />

            <div class="flex justify-between items-center">
              <h5 class="text-base">subtotal</h5>
              <span class="text-base font-semibold">$180</span>
            </div>
            <div class="flex justify-between items-center">
              <h5 class="text-base">Discount</h5>
              <span class="text-base font-semibold">-$15</span>
            </div>
            <div class="flex justify-between items-center">
              <h5 class="text-base">Delivery Free</h5>
              <span class="text-base font-semibold">$22</span>
            </div>
            <hr />

            <div class="flex justify-between items-center">
              <h5 class="text-base">Total</h5>
              <span class="text-2xl text-[#FFA91E] font-semibold">$187</span>
            </div>
          </div>
          <nuxt-link to="/shop/payment/process">
            <button
              class="bg-[#459D7A] rounded-md px-4 py-2.5 text-white hover:bg-green-800 duration-300"
            >
              procced to payment
            </button>
          </nuxt-link>
        </div>
      </div>
    </div>
    <RelatedProduct />
  </div>
</template>

<script setup lang="ts">
import {
  mastercardIcon,
  resultIcon,
  circleUser,
  deleteIcon,
  localShipping,
  editIcon,
  shoppingCart,
  restartIcon,
  infoIcon,
} from "~/public/Icons/icons";
import { ref } from "vue";
import { productData } from "~/contents/Data/productData";
import RelatedProduct from "~/components/relatedProduct.vue";

const selectedOption = ref("");
const selectOption = (option: string) => {
  selectedOption.value = option;
};
</script>
