<template>
  <div>
    <div class="relative w-full h-[90vh]">
      <img
        class="w-full h-full"
        :src="containerImage2"
        alt="container_Images"
      />
      <div
        class="absolute top-60 left-36 text-black w-[35%] flex flex-col items-start gap-6"
      >
        <h2 class="text-[40px] leading-[48.41px] font-semibold">
          Gift for your skin
        </h2>
        <p class="text-[20px] leading-[30px]">
          Aliquip fugiat ipsum nostrud ex et eu incididunt quis minim dolore
          excepteur voluptate
        </p>
      </div>
    </div>

    <div class="w-[90%] mx-auto mt-4">
      <div class="flex justify-between items-center mb-6">
        <div class="flex space-x-16">
          <button class="bg-[#459D7A] text-white py-2 px-12 rounded-lg">
            All Products
          </button>
          <button class="text-gray-700 hover:text-[#459D7A] px-10 py-2">
            Face
          </button>
          <button class="text-gray-700 hover:text-[#459D7A] px-10 py-2">
            Body
          </button>
        </div>
        <div class="flex gap-8">
          <div class="flex border-2 rounded px-3 py-2">
            <button>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                height="24px"
                viewBox="0 -960 960 960"
                width="24px"
                fill="#5f6368"
              >
                <path
                  d="M784-120 532-372q-30 24-69 38t-83 14q-109 0-184.5-75.5T120-580q0-109 75.5-184.5T380-840q109 0 184.5 75.5T640-580q0 44-14 83t-38 69l252 252-56 56ZM380-400q75 0 127.5-52.5T560-580q0-75-52.5-127.5T380-760q-75 0-127.5 52.5T200-580q0 75 52.5 127.5T380-400Z"
                />
              </svg>
            </button>
            <input
              type="text"
              placeholder="Search Product..."
              class="focus:outline-none pl-4"
            />
          </div>

          <button class="flex items-center gap-3">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              height="24px"
              viewBox="0 -960 960 960"
              width="24px"
              fill="#5f6368"
            >
              <path
                d="M400-240v-80h160v80H400ZM240-440v-80h480v80H240ZM120-640v-80h720v80H120Z"
              />
            </svg>
            Sort by
          </button>
        </div>
      </div>
    </div>

    <div class="w-[90%] mx-auto grid grid-cols-4 grid-rows-3 gap-4 my-8">
      <UiProductCard
        v-for="(product, index) in productData"
        :key="product.id"
        :scrImage="product.scrImage"
        :productTitle="product.productTitle"
        :definition="product.definition"
        :price="product.price"
        :promotionPrice="product.promotionPrice"
        :shopLink="product.shopLink"
        :productTranding="product.productTranding"
        :details="product.details"
      />
    </div>
  </div>
</template>

<script lang="ts" setup>
import { containerImage2 } from "../../assets/images/images";
import { productData } from "../../contents/Data/productData";
</script>
