<template>
  <div class="w-[90%] h-[10vh] flex justify-between items-center">
    <h1 class="font-bold text-[24px] leading-[29.05px]">Company_Name</h1>
    <div class="flex gap-16 justify-center items-center">
      <ul class="flex gap-6 text-[20px] leading-[24.2px]">
        <li>
          <NuxtLink to="/" active-class="text-green-500">Home</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/shop/shopPage" active-class="text-green-500"
            >Shop</NuxtLink
          >
        </li>
        <li>
          <NuxtLink to="/offers" active-class="text-green-500">Offers</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/ourStory" active-class="text-green-500"
            >Our Story</NuxtLink
          >
        </li>
        <li>
          <NuxtLink to="/blog" active-class="text-green-500">Blog</NuxtLink>
        </li>
      </ul>

      <div class="flex gap-4 justify-center items-center">
        <div
          class="relative text-sm focus-within:ring-0 focus-within:border-transparent"
        >
          <input
            type="text"
            placeholder="Search Product..."
            class="pl-4 pr-12 py-2 border border-gray-300 rounded-full focus:outline-none focus:ring-0 focus:border-transparent w-[170px]"
          />
          <button
            class="absolute right-2 top-1/2 transform -translate-y-1/2 text-gray-600 hover:text-gray-800 focus:outline-none"
          >
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
        </div>

        <nuxt-link to="/productHistory">
          <button
            class="flex px-3 py-2 rounded-full hover:text-green-800 font-semibold"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              height="24px"
              viewBox="0 -960 960 960"
              width="24px"
              class="fill-current hover:fill-green-800 transition-colors duration-300"
            >
              <path
                d="M280-80q-33 0-56.5-23.5T200-160q0-33 23.5-56.5T280-240q33 0 56.5 23.5T360-160q0 33-23.5 56.5T280-80Zm400 0q-33 0-56.5-23.5T600-160q0-33 23.5-56.5T680-240q33 0 56.5 23.5T760-160q0 33-23.5 56.5T680-80ZM246-720l96 200h280l110-200H246Zm-38-80h590q23 0 35 20.5t1 41.5L692-482q-11 20-29.5 31T622-440H324l-44 80h480v80H280q-45 0-68-39.5t-2-78.5l54-98-144-304H40v-80h130l38 80Zm134 280h280-280Z"
              />
            </svg>
            Cart (3)
          </button>
        </nuxt-link>

        <nuxt-link to="">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            height="24px"
            viewBox="0 -960 960 960"
            width="24px"
            class="hover:fill-green-500"
          >
            >
            <path
              d="M480-480q-66 0-113-47t-47-113q0-66 47-113t113-47q66 0 113 47t47 113q0 66-47 113t-113 47ZM160-160v-112q0-34 17.5-62.5T224-378q62-31 126-46.5T480-440q66 0 130 15.5T736-378q29 15 46.5 43.5T800-272v112H160Zm80-80h480v-32q0-11-5.5-20T700-306q-54-27-109-40.5T480-360q-56 0-111 13.5T260-306q-9 5-14.5 14t-5.5 20v32Zm240-320q33 0 56.5-23.5T560-640q0-33-23.5-56.5T480-720q-33 0-56.5 23.5T400-640q0 33 23.5 56.5T480-560Zm0-80Zm0 400Z"
            />
          </svg>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup></script>
