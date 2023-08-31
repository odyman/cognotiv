<script>
import feather from "feather-icons";

export default {
  data: () => {
    return {
      // Todo
    };
  },

  mounted() {
    feather.replace();
  },
  updated() {
    feather.replace();
  },
};
</script>

<template>
  <section
    class="
      flex flex-col
      sm:justify-between
      items-center
      sm:flex-row
      mt-12
      sm:mt-10
    "
  >
    <!-- Banner left contents -->
    <div class="w-full md:w-1/3 text-left">
      <h1
        class="
          font-general-semibold
          text-4xl
          md:text-4xl
          xl:text-6xl
          text-center
          sm:text-left
          text-yellow-500
          dark:text-yellow-500
          uppercase
        "
      >
       We Create
      </h1>
      <div class="flex justify-center sm:block">
        <NuxtLink
          to="/about"
          class="
            flex
            justify-center
            items-center
            w-68
            sm:w-98
            mt-12
            mb-6
            sm:mb-0
            text-lg
            border border-yellow-200
            dark:border-ternary-dark
            py-2.5
            sm:py-3
            px-5
            sm:px-8
            shadow-lg
            rounded-lg
            bg-transparent
            focus:ring-1 focus:ring-yellow-900
            hover:bg-yellow-500
            text-yellow-500
            hover:text-white
            duration-500
            "
          aria-label="Awesome Things"
        >
          <span class="text-sm sm:text-lg font-general-medium duration-100"
            >Awesome Things</span
          >
          <i
            data-feather="arrow-right"
            class="mr-1 sm:mr-1 ml-2 sm:ml-3 w-5 sm:w-6 duration-100"
          ></i>
        </NuxtLink>
      </div>
    </div>

    <!-- Banner right illustration -->
    <div class="w-full md:w-2/3 text-right float-right">
      <img
        v-if="this.$colorMode.value == 'dark'"
        src="~/static/developer-dark.svg"
        alt="Developer Dark"
      />
      <img v-else src="~/static/developer.svg" alt="Developer Light" />
    </div>
  </section>
</template>

<style lang="scss" scoped></style>
