<template>
  <div>
    <div class="relative h-[90vh]">
      <img class="h-full" :src="containerImage" alt="container_Images" />
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
        <nuxt-link to="/shop/shopPage">
          <button
            class="px-5 py-2.5 rounded bg-[#459D7A] text-base text-white hover:bg-green-700 duration-300"
          >
            Shop Now
          </button>
        </nuxt-link>
      </div>
    </div>
    <h1 class="text-center text-[40px] leading-[22px] font-bold mt-8 mb-12">
      Our Product
    </h1>
    <ShowingProduct />

    <div class="w-[90%] my-16 mx-auto flex justify-end items-center">
      <div class="w-[60%] flex justify-between items-center">
        <h2 class="text-[40px] leading-[22px] font-bold">Event Promotion</h2>
        <button
          class="text-[16px] leading-[22px] text-[#459D7A] hover:underline"
        >
          See all
        </button>
      </div>
    </div>

    <div class="w-full flex justify-center my-16">
      <div class="w-[90%] flex gap-8">
        <div class="relative rounded-xl drop-shadow-lg overflow-hidden">
          <img :src="promotionImage" alt="promotion Image" />
          <div class="absolute top-36 left-12 flex flex-col gap-[1.3rem]">
            <h2 class="text-[24px] leading-[29.03px] font-semibold">
              Relaxing & <br />
              Pampering
            </h2>
            <p class="text-[20px] leading-[30px]">
              Pariatur ad nisi ex tempor ea
            </p>
            <div>
              <Nuxt-link to="/eventPromotion">
                <button
                  class="bg-[#459D7A] px-8 rounded py-1.5 text-white hover:bg-green-800 duration-300"
                >
                  Explore
                </button>
              </Nuxt-link>
            </div>
          </div>
        </div>
        <div class="relative rounded-xl drop-shadow-lg overflow-hidden">
          <img :src="promotionImage2" alt="promotion Image2" />
          <div class="absolute top-36 left-12 flex flex-col gap-[1.3rem]">
            <h2 class="text-[24px] leading-[29.03px] font-semibold">
              Smooth & <br />
              Bright Skin
            </h2>
            <p class="text-[20px] leading-[30px]">
              Pariatur ad nisi ex tempor ea
            </p>
            <div>
              <Nuxt-link to="/eventPromotion">
                <button
                  class="bg-[#459D7A] px-8 rounded py-1.5 text-white hover:bg-green-800 duration-300"
                >
                  Explore
                </button>
              </Nuxt-link>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="w-[90%] mb-12 mt-6 mx-auto flex justify-end items-center">
      <div class="w-[56%] flex justify-between items-center">
        <h2 class="text-[40px] leading-[22px] font-bold">Our Story</h2>
        <button
          class="text-[16px] leading-[22px] text-[#459D7A] hover:underline"
        >
          See all
        </button>
      </div>
    </div>

    <div class="relative w-full h-[600px] mb-[1rem]">
      <img class="w-full h-full" :src="storyImage" alt="story_images" />
      <button
        class="flex items-center bg-black text-white absolute right-24 bottom-12 py-1.5 px-2"
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

    <div class="w-[90%] m-auto grid grid-cols-3 my-12 gap-6">
      <div class="flex flex-col justify-center p-4 gap-6">
        <h3 class="text-[28px] leading-[28px] font-bold">Read What's New</h3>
        <p class="text-16px leading-[26px]">
          Sint consequat in ipsum irure adipisicing dolore culpa incididunt.
          Veniam elit magna anim ipsum eiusmod eu
        </p>
        <div class="flex justify-between items-center pr-7">
          <button
            class="px-4 py-2 border-2 rounded border-[#459D7A] text-[#459D7A] hover:bg-[#459D7A] hover:text-white text-lg"
          >
            Explore more
          </button>
          <div>
            <button @click="previousCardSet" class="px-4 py-2">
              <svg
                class="text-green-200 fill-current"
                xmlns="http://www.w3.org/2000/svg"
                height="24px"
                viewBox="0 -960 960 960"
                width="24px"
                fill="#5f6368"
              >
                <path
                  d="m313-440 224 224-57 56-320-320 320-320 57 56-224 224h487v80H313Z"
                />
              </svg>
            </button>
            <button @click="nextCardSet" class="px-4 py-2">
              <svg
                class="text-[#459D7A] fill-current"
                xmlns="http://www.w3.org/2000/svg"
                height="24px"
                viewBox="0 -960 960 960"
                width="24px"
                fill="#5f6368"
              >
                <path
                  d="M647-440H160v-80h487L423-744l57-56 320 320-320 320-57-56 224-224Z"
                />
              </svg>
            </button>
          </div>
        </div>
      </div>
      <div
        v-for="(card, index) in [currentCardSet.leftCard]"
        :key="index"
        class="w-full bg-white rounded-lg overflow-hidden drop-shadow-2xl"
      >
        <img
          :src="card.contantImage"
          alt="Card Image"
          class="w-full mb-2 transition-transform duration-300 transform hover:scale-105"
        />
        <div class="p-4">
          <p class="font-semibold">{{ card.title }}</p>
          <p class="text-sm text-gray-400 mt-4">{{ card.date }}</p>
        </div>
      </div>

      <div
        v-for="(card, index) in [currentCardSet.rightCard]"
        :key="index"
        class="w-full bg-white drop-shadow-2xl rounded-lg overflow-hidden"
      >
        <img
          :src="card.contantImage"
          alt="Card Image"
          class="w-full mb-2 transition-transform duration-300 transform hover:scale-105"
        />
        <div class="p-4">
          <p class="font-semibold">{{ card.title }}</p>
          <p class="text-sm text-gray-400 mt-4">{{ card.date }}</p>
        </div>
      </div>
    </div>

    <div class="w-full flex flex-col justify-center items-center gap-2 mb-8">
      <h1 class="text-[40px] leading-[48.41px] font-semibold">Instagram</h1>
      <a href="" class="text-[20px] leading-[24.2px] font-serif italic"
        >@yourInstagram_offical</a
      >
    </div>
    <div class="grid grid-cols-6 grid-rows-2 w-[90%] mx-auto gap-2 mb-8">
      <div
        v-for="(image, index) in allIgImages"
        :key="index"
        class="overflow-hidden"
      >
        <a :href="image.igLink">
          <img
            :src="image.igImage"
            alt="ig_Images"
            class="transition-transform duration-300 transform hover:scale-105"
          />
        </a>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import {
  containerImage,
  promotionImage,
  promotionImage2,
  storyImage,
  productFeedBack,
  productFeedBack2,
  igImage,
  igImage2,
  igImage3,
  igImage4,
  igImage5,
  igImage6,
  igImage7,
  igImage8,
  igImage9,
  igImage10,
  igImage11,
  igImage12,
} from "~/assets/images/images";
import { ref, computed } from "vue";

interface Card {
  title: string;
  contantImage: string;
  date: string;
}
interface CardSet {
  leftCard: Card;
  rightCard: Card;
}

const cardSets = ref<CardSet[]>([
  {
    leftCard: {
      title: "Anim sint Lorem excepteur commodo ",
      contantImage: productFeedBack,
      date: "Oct 12, 2021",
    },
    rightCard: {
      title: "Adipisicing elit proident in elit magna deser",
      contantImage: productFeedBack2,
      date: "Oct 12, 2022",
    },
  },
  {
    leftCard: {
      title: "Summer Sale Promotion",
      contantImage: promotionImage,
      date: "Jul 01, 2023",
    },
    rightCard: {
      title: "Limited Time Offer",
      contantImage: promotionImage2,
      date: "Nov 21, 2024",
    },
  },
]);

const currentCardSetIndex = ref(0);
const currentCardSet = computed(
  () => cardSets.value[currentCardSetIndex.value]
);

const previousCardSet = () => {
  if (currentCardSetIndex.value > 0) {
    currentCardSetIndex.value--;
  } else {
    currentCardSetIndex.value = cardSets.value.length - 1;
  }
};

const nextCardSet = () => {
  if (currentCardSetIndex.value < cardSets.value.length - 1) {
    currentCardSetIndex.value++;
  } else {
    currentCardSetIndex.value = 0;
  }
};

const allIgImages = [
  {
    id: 1,
    igImage: igImage,
    igLink: "/",
  },
  {
    id: 2,
    igImage: igImage2,
    igLink: "/",
  },
  {
    id: 3,
    igImage: igImage3,
    igLink: "/",
  },
  {
    id: 4,
    igImage: igImage4,
    igLink: "/",
  },
  {
    id: 5,
    igImage: igImage5,
    igLink: "/",
  },
  {
    id: 6,
    igImage: igImage6,
    igLink: "/",
  },
  {
    id: 7,
    igImage: igImage7,
    igLink: "/",
  },
  {
    id: 8,
    igImage: igImage8,
    igLink: "/",
  },
  {
    id: 9,
    igImage: igImage9,
    igLink: "/",
  },
  {
    id: 10,
    igImage: igImage10,
    igLink: "/",
  },
  {
    id: 11,
    igImage: igImage11,
    igLink: "/",
  },
  {
    id: 12,
    igImage: igImage12,
    igLink: "/",
  },
];
</script>
