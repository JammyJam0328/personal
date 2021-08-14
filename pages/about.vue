<template>
  <div class="pb-14">
    <div class="container mx-auto px-5 sm:px-6 lg:px-8">
      <div class="md:ml-20">
        <div class="py-5">
          <nuxt-link to="/">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M11 19l-7-7 7-7m8 14l-7-7 7-7"
              />
            </svg>
          </nuxt-link>
        </div>
        <div
          class="font-bold text-2xl text-gray-600 flex items-center space-x-4"
        >
          <img
            src="../assets/tatInta3.jpg"
            class="flex-shrink-0 h-16 w-16 rounded-full ring-4 ring-pink-200"
            alt=""
          />
          <div>About</div>
        </div>
        <div class="mt-10">
          <blockquote>
            <span class="text-xl italic text-gray-500">
              "Tatwina is maganda "</span
            >
          </blockquote>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  transition: 'page',
}
</script>

<style>
.page-enter-active,
.page-leave-active {
  transition-property: opacity;
  transition-timing-function: ease-in-out;
  transition-duration: 300ms;
}
.page-enter,
.page-leave-to {
  opacity: 0;
}
body {
  background-color: #fef2f2;
}
</style>
