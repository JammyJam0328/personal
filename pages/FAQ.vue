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
        <div class="flex items-center justify-center w-full py-2">
          <img
            src="../assets/tatwina5.jpg"
            class="rounded-full h-16 w-16 shadow-md ring-4 ring-pink-200"
            alt=""
          />
        </div>
        <div class="bg-gray-50 shadow-md rounded-lg">
          <div class="max-w-7xl mx-auto py-12 px-4 sm:py-16 sm:px-6 lg:px-8">
            <div class="max-w-3xl mx-auto divide-y-2 divide-gray-200">
              <h2
                class="
                  text-center text-3xl
                  font-extrabold
                  text-gray-900
                  sm:text-4xl
                "
              >
                Frequently asked questions
              </h2>
              <dl class="mt-6 space-y-6 divide-y divide-gray-200">
                <div v-for="question in questions" :key="question.question">
                  <question :question="question" />
                </div>
              </dl>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Question from '../components/Question.vue'
export default {
  transition: 'page',
  components: {
    Question,
  },

  data() {
    return {
      questions: [
        {
          question: 'What is your favorite color ?',
          answer: 'Taupe',
        },
        {
          question: 'Question no 2',
          answer: 'answer 2',
        },
        {
          question: 'Question no 3',
          answer: 'answer 3',
        },
        {
          question: 'Question no 4',
          answer: 'answer 4',
        },
        {
          question: 'Question no 5',
          answer: 'answer 5',
        },
        {
          question: 'Question no 6',
          answer: 'answer 6',
        },
        {
          question: 'Question no 7',
          answer: 'answer 7',
        },
        {
          question: 'Question no 8',
          answer: 'answer 8',
        },
        {
          question: 'Question no 9',
          answer: 'answer 9',
        },
        {
          question: 'Question no 10',
          answer: 'answer 10',
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
