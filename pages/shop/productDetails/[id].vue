<template>
  <div class="w-[80%] mx-auto">
    <div class="flex w-full my-2">
      <div class="flex" v-for="(link, index) in rountLink" :key="index">
        <nuxt-link :to="link.Link"
          ><button :class="link.style">
            {{ link.linkName }}
            <img :src="link.iconLink" alt="" /></button
        ></nuxt-link>
      </div>
    </div>

    <div class="w-full grid grid-cols-2 my-8">
      <div class="flex">
        <div class="grid grid-rows-4">
          <div class="w-[100px] h-[125px] rounded-xl overflow-hidden">
            <img :src="thumbnail1" alt="Image_1" />
          </div>
          <div class="w-[100px] h-[125px] rounded-xl overflow-hidden">
            <img :src="thumbnail2" alt="Image_2" />
          </div>
          <div class="w-[100px] h-[125px] rounded-xl overflow-hidden">
            <img :src="thumbnail3" alt="Image_3" />
          </div>
          <div class="w-[100px] h-[125px] rounded-xl overflow-hidden">
            <img :src="thumbnail4" alt="Image_4" />
          </div>
        </div>
        <div class="h-[536px] rounded-[4px] relative">
          <img
            class="w-full h-full"
            :src="product?.scrImage"
            :alt="product?.productTitle"
          />
          <span
            class="bg-[#FFC970] text-[#774900] rounded-md absolute top-5 right-5"
            >{{ product?.productTranding }}</span
          >
        </div>
      </div>

      <div class="p-6 w-full flex flex-col gap-3">
        <div class="flex flex-col gap-2">
          <h2 class="text-[24px] leading-[28px] text-black font-semibold">
            {{ product?.productTitle }}
          </h2>
          <p class="text-[16px] leading-[26px]">
            {{ product?.definition }}
          </p>
        </div>

        <div class="flex items-center gap-4 my-1">
          <span class="text-[#459D7A] text-[40px] leading-[56px] font-bold"
            >${{ product?.promotionPrice }}</span
          >
          <span class="text-[#9095A0] text-[20px] leading-[30px]"
            >${{ product?.price }}</span
          >
        </div>

        <p class="text-[16px] leading-[26px]">
          {{ product?.details }}
        </p>

        <div class="flex gap-2.5 items-center my-1.5">
          <span class="text-sm text-gray-500"
            ><span class="text-[16px] leading-[26px] font-bold text-black">{{
              product?.review
            }}</span>
            reviews</span
          >
          <span class="text-sm text-gray-500"
            ><span class="text-[16px] leading-[26px] font-bold text-black">{{
              product?.soldNumber
            }}</span>
            sold</span
          >
          <ui-rating-star />
        </div>
        <div class="flex gap-2.5">
          <img :src="checkCircleIcon" alt="Check_Icon" />
          <p class="text-[16px] leading-[26px]">
            Free shipping on orders over $49USD
          </p>
        </div>

        <div class="flex gap-2.5">
          <img :src="checkCircleIcon" alt="Check_Icon" />
          <p class="text-[16px] leading-[26px]">Free + easy returns</p>
        </div>

        <div class="my-2">
          <label
            for="size"
            class="block text-[16px] leading-[26px] text-[#424955] font-semibold mb-1"
            >Choose size</label
          >
          <select id="size" class="border rounded-md p-2 w-full">
            <option class="text-sm font-semibold" value="48ml">50.00 ML</option>
            <option class="text-sm font-semibold" value="60ml">60.00 ML</option>
            <option class="text-sm font-semibold" value="74ml">75.00 ML</option>
            <option class="text-sm font-semibold" value="110ml">
              115.00 ML
            </option>
          </select>
        </div>

        <div class="mb-6">
          <label
            for="quantity"
            class="block text-[16px] leading-[26px] text-[#424955] font-semibold mb-1"
            >Quantity</label
          >
          <div class="flex items-center space-x-3">
            <button
              @click="decreaseQuantity"
              class="py-2 px-3.5 bg-[#f3f4f6] text-gray-600 rounded-md hover:bg-gray-400 duration-300"
            >
              -
            </button>
            <input
              type="text"
              :value="quantity"
              readonly
              class="w-12 text-center bg-[#f3f4f6] rounded-md py-2 px-3.5"
            />
            <button
              @click="increaseQuantity"
              class="py-2 px-3.5 bg-[#f3f4f6] text-gray-600 rounded-md hover:bg-gray-400 duration-300"
            >
              +
            </button>
          </div>

          <div class="flex space-x-4 mt-4">
            <button
              class="flex items-center justify-center flex-1 gap-2 border-[#459D7A] border-2 text-[#459D7A] py-2 rounded-md hover:bg-green-700 hover:text-white duration-300"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                height="20px"
                class="text-[#459D7A] fill-current"
                viewBox="0 -960 960 960"
                width="20px"
              >
                <path
                  d="M444-576v-132H312v-72h132v-132h72v132h132v72H516v132h-72ZM263.79-96Q234-96 213-117.21t-21-51Q192-198 213.21-219t51-21Q294-240 315-218.79t21 51Q336-138 314.79-117t-51 21Zm432 0Q666-96 645-117.21t-21-51Q624-198 645.21-219t51-21Q726-240 747-218.79t21 51Q768-138 746.79-117t-51 21ZM48-792v-72h133l155 360h301l113-264h78L703-476q-9 20-26.5 32T637-432H317l-42 72h493v72H276q-42 0-63-36.5t0-71.5l52-90-131-306H48Z"
                />
              </svg>
              Add to bag
            </button>
            <nuxt-link to="/shop/payment/orderReview">
              <button
                class="flex items-center justify-center flex-1 bg-[#459D7A] text-white px-24 py-2 rounded-md hover:bg-green-800 duration-300"
              >
                Checkout
              </button>
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
    <related-product />

    <div class="w-full flex flex-col justify-center items-start gap-12 my-10">
      <h1 class="text-start text-[40px] leading-[26px] font-semibold my-4">
        Ingredients Cards
      </h1>
      <div class="grid grid-cols-3 gap-10">
        <ui-ingredients-cards />
      </div>
      <div class="w-full flex justify-center">
        <button
          class="px-16 py-2 text-[16px] leading-[22px] rounded-lg border-2 border-[#459D7A] text-[#459D7A] hover:bg-[#459D7A] hover:text-white duration-300"
        >
          See full list
        </button>
      </div>
    </div>

    <div>
      <h1 class="text-start text-[40px] leading-[26px] font-semibold my-4">
        How to use
      </h1>

      <div class="relative">
        <img :src="howToUse" alt="playing_video" />
        <button
          class="flex items-center bg-black text-white absolute right-[43.3%] top-[50%] py-1.5 px-2"
        >
          Watch Video
          <svg
            xmlns="http://www.w3.org/2000/svg"
            height="24px"
            viewBox="0 -960 960 960"
            width="24px"
            fill="#5f6368"
          >
            <path
              d="M320-200v-560l440 280-440 280Zm80-280Zm0 134 210-134-210-134v268Z"
            />
          </svg>
        </button>
      </div>

      <div class="flex justify-between items-center my-8">
        <h2 class="text text-[40px] leading-[26px] font-semibold">Reviews</h2>
        <button
          class="text-green-500 border border-[#459D79] px-4 py-2 rounded-md text-md hover:bg-green-100 duration-300 flex gap-2"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            height="20px"
            viewBox="0 -960 960 960"
            width="20px"
            fill="#459D79"
          >
            <path
              d="M96 0v-192h768V0H96Zm168-360h51l279-279-26-27-25-24-279 279v51Zm-72 72v-152.92L594-843q11-11 23.84-16 12.83-5 27-5 14.16 0 27.16 5t24.1 15.94L747-792q11 11 16 24t5 27.4q0 13.49-4.95 26.54-4.95 13.05-15.75 23.85L345-288H192Zm503-455-51-49 51 49ZM594-639l-26-27-25-24 51 51Z"
            />
          </svg>
          Write a review
        </button>
      </div>

      <div class="grid grid-cols-2 gap-4">
        <div class="flex flex-col p-4">
          <div class="flex items-center gap-4">
            <ui-review-star /> <span> {{ product?.review }} Reviews</span>
          </div>
          <div class="space-y-4 mt-4">
            <div
              v-for="rating in ratings"
              :key="rating.stars"
              class="flex items-center"
            >
              <span class="text-[14px] leading-[22px]">{{ rating.stars }}</span>
              <svg
                class="w-[24px] h-[24px] text-[#F3c63f] mx-2"
                fill="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  d="M12 2l3.09 6.26L22 9.27l-5 4.87L18.18 22 12 18.27 5.82 22 7 14.14l-5-4.87 6.91-1L12 2z"
                />
              </svg>
              <div class="rounded-full w-64 h-2 bg-[#DEE1E6] ml-2 relative">
                <div
                  :style="{ width: rating.width }"
                  class="bg-[#F3c63f] h-2 rounded-full"
                ></div>
              </div>
              <span class="ml-2 text-[14px] leading-[22px] text-black"
                >{{ rating.percentage }}%</span
              >
            </div>
          </div>
        </div>

        <div class="flex flex-col gap-4">
          <div
            v-for="review in customerReviews"
            :key="review.name"
            class="flex items-start gap-2"
          >
            <img
              :src="review.avatar"
              alt="Avatar"
              class="w-[44px] h-[44px] rounded-full mr-4"
            />
            <div>
              <div class="flex items-center gap-2">
                <span class="font-bold">{{ review.name }}</span>
                <span class="text-gray-500 text-sm">{{ review.time }} ago</span>
              </div>

              <div class="flex items-center mt-1">
                <div v-for="n in 5" :key="n" class="text-yellow-500">
                  <svg
                    v-if="n <= review.rating"
                    xmlns="http://www.w3.org/2000/svg"
                    fill="currentColor"
                    viewBox="0 0 24 24"
                    class="w-4 h-4"
                  >
                    <path
                      d="M12 2l3.09 6.26L22 9.27l-5 4.87L18.18 22 12 18.27 5.82 22 7 14.14l-5-4.87 6.91-1L12 2z"
                    />
                  </svg>
                  <svg
                    v-else
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    viewBox="0 0 24 24"
                    class="w-4 h-4"
                  >
                    <path
                      d="M12 2l3.09 6.26L22 9.27l-5 4.87L18.18 22 12 18.27 5.82 22 7 14.14l-5-4.87 6.91-1L12 2z"
                    />
                  </svg>
                </div>
              </div>
              <p class="text-gray-700 mt-2 line-clamp-3">
                {{ review.comment }}
              </p>
            </div>
          </div>
          <div class="ml-12 flex items-center gap-5 mt-4">
            <button>
              <img :src="arowLeftIcon" alt="icon_left" />
            </button>
            <button
              v-for="page in pages"
              :key="page"
              class="px-3 py-1 border rounded-full"
              :class="{
                'border border-[#459D7A] text-[#459D7A]': page === currentPage,
              }"
            >
              {{ page }}
            </button>
            <button>
              <img :src="arrowForwardRightIcon" alt="icon_right" />
            </button>
          </div>
        </div>
      </div>

      <Faqs />
    </div>
  </div>
</template>

<script setup lang="ts">
import { onMounted, ref } from "vue";
import { useRoute } from "nuxt/app";
import { productData } from "~/contents/Data/productData";
import {
  arrowForwardRightIcon,
  checkCircleIcon,
  arowLeftIcon,
} from "@/public/Icons/icons";
import {
  thumbnail1,
  thumbnail2,
  thumbnail3,
  thumbnail4,
  howToUse,
} from "@/assets/images/images";
import { pf_1, pf_2, pf_3 } from "@/static/productScr";

const rountLink = [
  {
    style: "text-[#459D7A] flex gap-3 items-center text-[16px] leading-[28px]",
    linkName: "Home",
    iconLink: arrowForwardRightIcon,
    Link: "/",
  },
  {
    style:
      "text-[#459D7A] ml-2 flex gap-3 items-center text-[16px] leading-[28px]",
    linkName: "Shop",
    iconLink: arrowForwardRightIcon,
    Link: "/",
  },
  {
    style:
      "text-[#459D7A] flex ml-2 gap-3 items-center text-[16px] leading-[28px]",
    linkName: "Product Type",
    iconLink: arrowForwardRightIcon,
    Link: "/shop/shopPage",
  },
  {
    style:
      "hover:text-[#459D7A] flex ml-2 gap-3  items-center text-[16px] leading-[28px]",
    linkName: "Detail",
    iconLink: "",
    Link: "/shop/shopPage",
  },
];

const ratings = [
  { stars: 5, percentage: 60, width: "60%" },
  { stars: 4, percentage: 25, width: "25%" },
  { stars: 3, percentage: 10, width: "10%" },
  { stars: 2, percentage: 5, width: "5%" },
  { stars: 1, percentage: 0, width: "0%" },
];

const customerReviews = [
  {
    name: "Annie Haley",
    avatar: pf_1,
    time: "3d",
    comment:
      "I’m absolutely thrilled with this product! The quality is outstanding and it exceeded all my expectations. The attention to detail is evident, and it’s clear that a lot of care went into its design. I highly recommend it to anyone looking for something reliable and well-made.",
    rating: 5,
  },
  {
    name: "Green William",
    avatar: pf_2,
    time: "3d",
    comment:
      "The service provided was top-notch from start to finish. The staff was incredibly friendly and knowledgeable, and they went above and beyond to ensure my needs were met. It’s rare to find such dedicated and attentive service. I’ll definitely be coming back!",
    rating: 4,
  },
  {
    name: "James Rower",
    avatar: pf_3,
    time: "3d",
    comment:
      "Great job on this project! Your creativity and hard work really shine through. The final result is impressive and exactly what we were hoping for. Your attention to detail and commitment to excellence are greatly appreciated. Looking forward to working with you again!",
    rating: 3,
  },
];

const pages = [1, 2, 3, 4, 5];
const currentPage = 2;

const quantity = ref(1);

const increaseQuantity = () => {
  quantity.value++;
};

const decreaseQuantity = () => {
  if (quantity.value > 1) {
    quantity.value--;
  }
};

interface Product {
  id: number;
  productTitle: string;
  definition: string;
  scrImage: string;
  price: number;
  promotionPrice: number;
  shopLink: string;
  typeProduct: string;
  productTranding: string;
  review: number;
  soldNumber: number;
  details: string;
}

const route = useRoute();
const id = Number(route.params.id);

const product = ref<Product | undefined>();

onMounted(() => {
  product.value = productData.find((p) => p.id === id);
  if (!product.value) {
    console.log(`Product with ID ${id} not found`);
  }
});
</script>
