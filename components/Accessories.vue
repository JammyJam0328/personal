<template>
  <div class="group relative">
    <div
      class="
        w-full
        min-h-80
        bg-gray-200
        aspect-w-1 aspect-h-1
        rounded-md
        overflow-hidden
        group-hover:opacity-75
        lg:h-80 lg:aspect-none
        border-2 border-gray-300
      "
    >
      <img
        :src="accessory.accsImgUrl"
        alt="Front of men&#039;s Basic Tee in black."
        class="w-full h-full object-center object-cover lg:w-full lg:h-full"
      />
    </div>
    <div class="mt-4 flex justify-between">
      <div>
        <h3 class="text-lg text-gray-700">
          <a :href="accessory.accsUrl" target="_blank">
            <span aria-hidden="true" class="absolute inset-0"></span>
            {{ accessory.accs }}
          </a>
        </h3>
        <blockquote v-if="accessory.desc">
          <p class="mt-1 text-sm text-gray-500 italic">
            "{{ accessory.desc }}"
          </p>
        </blockquote>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['accessory'],
}
</script>
