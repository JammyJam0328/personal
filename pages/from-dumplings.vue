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
        <div class="pb-5 grid justify-center text-xl w-full">
          <img
            src="../assets/tatwinaicon.jpg"
            class="h-16 w-16 rounded-full mx-auto ring-4 ring-pink-200"
            alt=""
          />
          <div>&#129375; &#128248; Dumplings Captured &#128248; &#129375;</div>
        </div>
        <div class="bg-white rounded-md shadow">
          <div
            class="
              pt-5
              max-w-2xl
              mx-auto
              pb-12
              px-4
              sm:py-24 sm:px-6
              lg:max-w-7xl lg:px-8
            "
          >
            <div
              class="
                grid grid-cols-1
                gap-y-10 gap-x-6
                sm:grid-cols-2
                lg:grid-cols-4
                xl:gap-x-8
              "
            >
              <div v-for="img in tatImages" :key="img.imgUrl">
                <TatImage :img="img" />
              </div>

              <!-- More products... -->
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// images
import tat1 from '../assets/captured/tat1.jpg'
import tat2 from '../assets/captured/tat2.jpg'
import tat3 from '../assets/captured/tat3.jpg'
import tat4 from '../assets/captured/tat4.jpg'
import tat5 from '../assets/captured/tat5.jpg'

//
import TatImage from '../components/TatImage.vue'
export default {
  transitions: 'page',
  components: {
    TatImage,
  },

  data() {
    return {
      id: 0,
      tatImages: [
        {
          by: "Tatwina'sDumpling @jooommyyjam",
          tatImg: tat1,
        },
        {
          by: "Tatwina'sDumpling @jooommyyjam",
          tatImg: tat2,
        },
        {
          by: "Tatwina'sDumpling @jooommyyjam",
          tatImg: tat3,
        },
        {
          by: "Tatwina'sDumpling @jooommyyjam",
          tatImg: tat4,
        },
        {
          by: "Tatwina'sDumpling @jooommyyjam",
          tatImg: tat5,
        },

        {
          by: 'tatattheloml @_alexadbhdjs',
          tatImg:
            'https://pbs.twimg.com/media/E9UoYJBVIAIFnro?format=jpg&name=large',
        },

        {
          by: 'tatattheloml @_alexadbhdjs',
          tatImg:
            'https://pbs.twimg.com/media/E9Uouw5VgAYxMqC?format=jpg&name=large',
        },
        {
          by: 'tatreng @tatreng',
          tatImg:
            'https://pbs.twimg.com/media/E9Uo0oVUUAIQFE8?format=jpg&name=medium',
        },

        {
          by: 'hourly katrina ♡ @tatwinaloml',
          tatImg:
            'https://pbs.twimg.com/media/E9Uo5tCUYAQE0E-?format=jpg&name=large',
        },
        {
          by: 'hourly katrina ♡ @tatwinaloml',
          tatImg:
            'https://pbs.twimg.com/media/E9Uo59jVoAw3s7g?format=jpg&name=large',
        },
        {
          by: 'cherry @tatwinapics',
          tatImg:
            'https://pbs.twimg.com/media/E9UpWg7UcAQ8HlK?format=jpg&name=large',
        },
        {
          by: 'cherry @tatwinapics',
          tatImg:
            'https://pbs.twimg.com/media/E9UpYICVoAIgNPr?format=jpg&name=large',
        },
      ],
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
