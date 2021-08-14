<template>
  <div class="w-full pb-2">
    <div>
      <div class="">
        <div class="border-t-2 border-pink-200">
          <nav class="-mb-px flex justify-center" aria-label="Tabs">
            <!-- Current: "border-indigo-500 text-indigo-600", Default: "border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-300" -->
            <a
              v-on:click="changeTab('clothing')"
              v-bind:class="
                cTab == 'clothing'
                  ? 'border-indigo-600 text-indigo-600'
                  : 'text-gray-500'
              "
              href="#"
              class="
                border-transparent
                hover:text-gray-700 hover:border-gray-300
                w-1/4
                py-4
                px-1
                text-center
                border-b-2
                font-medium
                text-sm
              "
            >
              Clothing
            </a>

            <a
              v-on:click="changeTab('accessories')"
              v-bind:class="
                cTab == 'accessories'
                  ? 'border-indigo-600 text-indigo-600'
                  : 'text-gray-500'
              "
              href="#"
              class="
                border-transparent
                text-gray-500
                hover:text-gray-700 hover:border-gray-300
                w-1/4
                py-4
                px-1
                text-center
                border-b-2
                font-medium
                text-sm
              "
            >
              Accessories
            </a>

            <a
              v-on:click="changeTab('others')"
              v-bind:class="
                cTab == 'others'
                  ? 'border-indigo-600 text-indigo-600'
                  : 'text-gray-500'
              "
              href="#"
              class="
                border-transparent
                text-gray-500
                hover:text-gray-700 hover:border-gray-300
                w-1/4
                py-4
                px-1
                text-center
                border-b-2
                font-medium
                text-sm
              "
            >
              Others
            </a>
          </nav>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    changeTab(tab) {
      this.cTab = tab
      this.$emit('tabFromChild', this.cTab)
    },
  },
  data() {
    return {
      cTab: 'clothing',
    }
  },
}
</script>
