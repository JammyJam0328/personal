<template>
  <div class="pb-14">
    <div class="container mx-auto mt-5 px-5 sm:px-6 lg:px-8">
      <div class="mt:10 md:mt-24 md:ml-20">
        <div class="grid md:flex space-y-2 items-center">
          <transition
            enter-active-class="transition transform duration-1000 ease-out"
            enter-class="rotate-90 scale-50 opacity-o"
            enter-to-class="rotate-0 scale-100 opacity-100"
          >
            <div v-show="enterAnimation" class="mr-4 flex-shrink-0">
              <img
                src="../assets/tatwina2.jpg"
                class="h-32 w-32 rounded-full ring-4 ring-pink-200"
                alt=""
              />
            </div>
          </transition>
          <div class="text-gray-700">
            <div>
              <h4 class="text-4xl font-bold">Hi, I'm tatwina_</h4>
              <p class="mt-1">Content creator in TikTok and YouTube</p>
            </div>
          </div>
        </div>

        <social-media />
        <!-- This example requires Tailwind CSS v2.0+ -->
        <div class="relative">
          <div class="absolute inset-0 flex items-center" aria-hidden="true">
            <div class="w-full border-t border-gray-300"></div>
          </div>
          <div class="relative flex justify-center">
            <span class="px-2 bg-red-50 text-sm text-gray-500">
              &#129375; Dumplings Corner &#129375;
            </span>
          </div>
        </div>

        <tab />
      </div>
    </div>
  </div>
</template>

<script>
import SocialMedia from '../components/SocialMedia.vue'
import Tab from '../components/Tab.vue'
export default {
  transition: 'page',

  components: {
    SocialMedia,
    Tab,
  },

  mounted() {
    this.enterAnimation = true
  },

  data() {
    return {
      enterAnimation: false,
    }
  },
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
