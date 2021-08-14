<template>
  <div class="mt-3 flex justify-center md:justify-center">
    <div
      role="list"
      class="
        grid grid-cols-1
        gap-4
        sm:grid-cols-2
        md:grid-cols-3
        lg:grid-cols-4
      "
    >
      <NuxtLink to="/FAQ" class="bg-transparent">
        <div
          class="
            col-span-1
            flex flex-col
            h-52
            w-full
            md:w-64
            text-center
            bg-white
            rounded-lg
            shadow
            relative
            divide-y divide-gray-200
            transition
            duration-500
            ease-in-out
            transform
            hover:-translate-y-1 hover:scale-110
          "
        >
          <img
            src="../assets/tatInta1.jpg"
            class="absolute w-full h-full opacity-60 rounded-lg"
            alt=""
          />
          <div class="flex-1 flex flex-col p-8 z-30 justify-center">
            <h3 class="text-gray-50 text-4xl font-medium">FAQ's</h3>
          </div>
        </div>
      </NuxtLink>

      <NuxtLink to="/budol" class="bg-transparent">
        <div
          class="
            col-span-1
            flex flex-col
            h-52
            w-64
            text-center
            bg-white
            rounded-lg
            shadow
            relative
            divide-y divide-gray-200
            transition
            duration-500
            ease-in-out
            transform
            hover:-translate-y-1 hover:scale-110
          "
        >
          <img
            src="../assets/tatwina3.jpg"
            class="absolute w-full h-full opacity-60 rounded-lg"
            alt=""
          />
          <div class="flex-1 flex flex-col p-8 z-30 justify-center">
            <h3 class="text-gray-50 text-xl">&#128717; @tatwina's Budols</h3>
          </div>
        </div>
      </NuxtLink>
      <NuxtLink to="/about" class="bg-transparent">
        <div
          class="
            col-span-1
            flex flex-col
            h-52
            w-64
            text-center
            bg-white
            rounded-lg
            shadow
            relative
            divide-y divide-gray-200
            transition
            duration-500
            ease-in-out
            transform
            hover:-translate-y-1 hover:scale-110
          "
        >
          <img
            src="../assets/tatwina5.jpg"
            class="absolute w-full h-full opacity-60 rounded-lg"
            alt=""
          />
          <div class="flex-1 flex flex-col p-8 z-30 justify-center">
            <h3 class="text-gray-50 text-2xl font-medium">About Tatwina</h3>
          </div>
        </div>
      </NuxtLink>
      <NuxtLink to="/from-dumplings" class="bg-transparent">
        <div
          class="
            col-span-1
            flex flex-col
            h-52
            w-64
            text-center
            bg-white
            rounded-lg
            shadow
            relative
            divide-y divide-gray-200
            transition
            duration-500
            ease-in-out
            transform
            hover:-translate-y-1 hover:scale-110
          "
        >
          <img
            src="../assets/tatwina6.jpg"
            class="absolute w-full h-full opacity-60 rounded-lg"
            alt=""
          />
          <div class="flex-1 flex flex-col p-8 z-30 justify-center">
            <h3 class="text-gray-50 text-4xl font-medium">
              Dumplings Captured
            </h3>
          </div>
        </div>
      </NuxtLink>
    </div>
  </div>
</template>
