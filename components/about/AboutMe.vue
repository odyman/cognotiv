<script>
import Button from "../reusable/Button.vue";
import { mapState } from "vuex";

export default {
  components: { Button },
  data: () => {
    return {
      // @todo
    };
  },
  computed: {
    ...mapState(["aboutUsHeading","aboutUs"]),
  },
};
</script>

<template>
  <div class="block sm:flex sm:gap-10 mt-10 sm:mt-20">
    
    <div
      class="
        leading-loose
        max-w-xl
        m-4
        p-7
        bg-gray-300
        dark:bg-secondary-dark
        rounded-xl
        shadow-xl
        text-left
      "
    >
      <!-- About details -->
      <div class="w-full text-left">
        <h1
          class="
            font-general-semibold
            text-2xl
            md:text-3xl
            xl:text-4xl
            text-center
            sm:text-left
            text-ternary-dark
            dark:text-ternary-light
            pb-5
            sm:pb-3
          "
        >{{ aboutUsHeading }}</h1>
        <p
          class="
            font-general-regular
            mb-4
            text-ternary-dark
            dark:text-ternary-light
            text-lg
          "
        >
          {{ aboutUs }}
        </p>
      </div>
      <div class="mt-6">
        <NuxtLink to="/about">
          <Button
            title="Learn more"
            class="
              px-4
              py-2.5
              text-white
              tracking-wider
              bg-yellow-500
              hover:bg-yellow-600
              focus:ring-1 focus:ring-yellow-900
              rounded-lg
              duration-500
            "
            type="button"
            aria-label="Learn more"
          />
        </NuxtLink>
      </div> 
      <div class="w-full md:w-1/2"></div>
    </div>
    
  </div>
</template>
