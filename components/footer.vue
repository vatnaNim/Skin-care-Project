<template>
  <footer class="bg-gray-900 text-white py-24 w-full">
    <div class="w-[90%] mx-auto grid grid-cols-2 text-[14px] leading-[22px]">
      <div class="grid grid-cols-3">
        <div>
          <h5 class="font-semibold mb-3">About</h5>
          <ul class="space-y-2">
            <li v-for="(item, index) in aboutMenu" :key="index">
              <NuxtLink to="item.link" class="hover:underline">{{
                item.listName
              }}</NuxtLink>
            </li>
          </ul>
          <div class="mt-6">
            <select class="bg-gray-800 text-white py-2 px-3 rounded">
              <option>English</option>
              <option>Spanish</option>
              <option>Cambodian</option>
            </select>
          </div>
        </div>

        <div>
          <h5 class="font-semibold mb-3">Help</h5>
          <ul class="space-y-2">
            <li v-for="(item, index) in helpMenu" :key="index">
              <NuxtLink to="item.link" class="hover:underline">{{
                item.listName
              }}</NuxtLink>
            </li>
          </ul>
        </div>

        <div>
          <h5 class="font-semibold mb-3">Contact</h5>
          <p class="mb-4">
            Phone:
            <a href="tel:+1234567890" class="hover:underline"
              >(+1) 123 456 7890</a
            >
          </p>
          <p>
            Email:
            <a href="mailto:name@email.com" class="hover:underline"
              >name@email.com</a
            >
          </p>
        </div>
      </div>

      <div class="flex flex-col mx-auto gap-1">
        <h5 class="font-semibold mb-3">Receive new promotions</h5>
        <p class="text-gray-400 text-sm mb-4">
          Duis ac tempor commodo sed reprehende.
        </p>

        <div class="flex">
          <div class="relative">
            <svg
              class="absolute left-3 top-1/2 transform -translate-y-1/2 w-5 h-5 text-gray-500"
              xmlns="http://www.w3.org/2000/svg"
              height="24px"
              viewBox="0 -960 960 960"
              width="24px"
              fill="#5f6368"
            >
              <path
                d="M160-160q-33 0-56.5-23.5T80-240v-480q0-33 23.5-56.5T160-800h640q33 0 56.5 23.5T880-720v480q0 33-23.5 56.5T800-160H160Zm320-280L160-640v400h640v-400L480-440Zm0-80 320-200H160l320 200ZM160-640v-80 480-400Z"
              />
            </svg>
            <input
              type="email"
              placeholder="Input your email"
              class="w-full p-2 pl-10 bg-gray-800 text-white rounded-l-md focus:outline-none focus:ring-0"
            />
          </div>
          <button
            class="bg-green-500 hover:bg-green-600 text-white py-2 px-4 rounded-r-md"
          >
            Subscribe
          </button>
        </div>

        <div class="mt-4 flex space-x-4">
          <NavLink href="#" class="hover:text-gray-400">
            <img class="w-[20px]" :src="xIcon" alt="x_icons"
          /></NavLink>
          <NavLink href="#" class="hover:text-gray-400">
            <img class="w-[20px]" :src="faceBookIcon" alt="Facebook_icons"
          /></NavLink>
          <NavLink href="#" class="hover:text-gray-400">
            <img class="w-[20px]" :src="linkedInIcon" alt="LinkedIn_icons"
          /></NavLink>
          <NavLink href="#" class="hover:text-gray-400">
            <img class="w-[20px]" :src="youTubeIcon" alt="YouTube_icons"
          /></NavLink>
        </div>
        <div class="mt-4 flex gap-4 text-gray-400">
          <p>&copy; 2022 Brand, Inc.</p>
          <div class="space-x-4">
            <a href="#" class="hover:underline">. Privacy</a>
            <a href="#" class="hover:underline">. Terms</a>
            <a href="#" class="hover:underline">. Sitemap</a>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import {
  faceBookIcon,
  linkedInIcon,
  xIcon,
  youTubeIcon,
} from "~/public/Icons/icons";

const aboutMenu = [
  { listName: "Home", link: "/" },
  { listName: "Shop", link: "/shop" },
  { listName: "Our Story", link: "/our-story" },
  { listName: "Blogs", link: "/blogs" },
];

const helpMenu = [
  { listName: "Shipping & Returns", link: "/shipping-returns" },
  { listName: "Track Order", link: "/track-order" },
  { listName: "FAQs", link: "/faqs" },
];
</script>
