<template>
  <div class="mt-2">
    <dt class="text-lg">
      <!-- Expand/collapse question button -->
      <button
        v-on:click="isOpen = !isOpen"
        type="button"
        class="text-left w-full flex justify-between items-start text-gray-400"
        aria-controls="faq-0"
        aria-expanded="false"
      >
        <span class="font-medium text-gray-900">
          {{ question.question }}
        </span>
        <span class="ml-6 h-7 flex items-center">
          <svg
            v-bind:class="isOpen ? 'rotate-180' : 'rotate-0'"
            class="rh-6 w-6 transform"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            aria-hidden="true"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M19 9l-7 7-7-7"
            />
          </svg>
        </span>
      </button>
    </dt>
    <transition
      enter-active-class="transform transition duration-500 ease-custom"
      enter-class="-translate-y-1/2 scale-y-0 opacity-0"
      enter-to-class="translate-y-0 scale-y-100 opacity-100"
      leave-active-class="transform transition duration-300 ease-custom"
      leave-class="translate-y-0 scale-y-100 opacity-100"
      leave-to-class="-translate-y-1/2 scale-y-0 opacity-0"
    >
      <dd v-show="isOpen" class="mt-2 pr-12" id="faq-0">
        <p class="text-base text-gray-500">
          {{ question.answer }}
        </p>
      </dd>
    </transition>
  </div>
</template>

<script>
export default {
  props: ['question'],
  data() {
    return {
      isOpen: false,
    }
  },
}
</script>
