<template>
  <div class="w-[768px] h-full space-y-5 my-5">
    <span class="text-center space-y-10">
      <h1 class="text-4xl font-semibold">Product history</h1>
      <p class="base text-[#9095A0]">
        Check the status of recent orders, manage returns, and <br />
        discover similar products.
      </p>
    </span>

    <div
      v-for="(order, index) in orders"
      :key="order.id"
      class="w-full rounded-lg border shadow-md flex flex-col gap-5"
    >
      <div
        @click="toggleOrderDetails(index)"
        class="flex justify-between items-center cursor-pointer px-5 py-4 hover:bg-green-100"
      >
        <div class="w-full flex justify-between items-center">
          <div class="space-x-3 *:text-sm">
            <span class="text-[#9095a0]"
              >Delivery on {{ order.deliveryDate }}</span
            >
            <span class="font-semibold">Order #{{ order.orderNumber }}</span>
          </div>

          <div class="flex items-center space-x-4 text-sm text-[#9095a0]">
            <button
              class="underline underline-offset-4 hover:text-[#459d7a] duration-300"
            >
              Manage order
            </button>
            <button
              class="underline underline-offset-4 hover:text-[#459d7a] duration-300"
            >
              View invoice
            </button>
            <button>
              <svg
                v-if="!isOrderDetailsVisible[index]"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                class="w-[20px] h-[20px] text-bold text-black"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M9 5l7 7-7 7"
                />
              </svg>
              <svg
                v-else
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                class="w-[20px] h-[20px] text-bold text-black"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                />
              </svg>
            </button>
          </div>
        </div>
      </div>

      <div
        v-if="isOrderDetailsVisible[index]"
        class="space-y-6 transition-all duration-300"
      >
        <div
          v-for="(product, pIndex) in order.products"
          :key="pIndex"
          class="w-full flex justify-between items-center space-x-4 px-5 py-4"
        >
          <div class="flex items-center gap-6">
            <img
              :src="product.image"
              alt="Product"
              class="w-[101px] h-[127px] rounded-lg object-cover"
            />
            <div class="flex flex-col gap-4">
              <div class="space-y-2">
                <h5 class="text-base font-semibold">{{ product.name }}</h5>
                <div
                  class="flex gap-3 *:bg-[#f3f4f6] *:px-4 *:py-1 *:rounded-full text-xs"
                >
                  <span> x{{ product.quantity }} </span>
                  <span>{{ product.size }}</span>
                </div>
              </div>
              <span class="font-semibold text-base">{{ product.price }}</span>
            </div>
          </div>

          <div class="flex flex-col space-y-3">
            <button
              class="bg-[#459D7A] text-white text-sm px-9 py-2 rounded hover:bg-green-800 duration-300"
            >
              Buy again
            </button>
            <button
              class="bg-[#f3f4f6] text-[#565f6c] text-sm px-9 py-2 rounded hover:bg-gray-300 duration-300"
            >
              View product
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import {
  productImage,
  productImage12,
  productImage5,
  productImage3,
  productImage2,
} from "~/static/productScr";

const orders = ref([
  {
    id: 1,
    deliveryDate: "September 22, 2024",
    orderNumber: 4376,
    products: [
      {
        name: "Product name",
        quantity: 2,
        size: "60ml",
        price: "$104",
        image: productImage5,
      },
      {
        name: "Product name",
        quantity: 1,
        size: "50ml",
        price: "$76",
        image: productImage,
      },
    ],
  },
  {
    id: 2,
    deliveryDate: "December 25, 2023",
    orderNumber: 5001,
    products: [
      {
        name: "Product name",
        quantity: 4,
        size: "60ml",
        price: "$18",
        image: productImage,
      },
      {
        name: "Product name",
        quantity: 6,
        size: "50ml",
        price: "$96",
        image: productImage12,
      },
    ],
  },
  {
    id: 3,
    deliveryDate: "June 22, 2022",
    orderNumber: 1168,
    products: [
      {
        name: "Product name",
        quantity: 1,
        size: "50ml",
        price: "$104",
        image: productImage2,
      },
      {
        name: "Product name",
        quantity: 5,
        size: "50ml",
        price: "$76",
        image: productImage3,
      },
    ],
  },
]);

const isOrderDetailsVisible = ref(orders.value.map((_, index) => index === 0));
const toggleOrderDetails = (index: number) => {
  isOrderDetailsVisible.value[index] = !isOrderDetailsVisible.value[index];
};
</script>
