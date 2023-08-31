<script>
import Button from "../reusable/Button.vue";
export default {
  components: { Button },
  data: () => {
    return {
      // @todo
    };
  },
};
</script>

<template>
  <!-- Contact form -->
  <div class="w-full md:w-1/2">
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
      <form
        @submit="
          (e) => {
            e.preventDefault;
          }
        "
        class="font-general-regular space-y-7"
      >
        <div class="">
          <label
            class="block text-lg text-primary-dark dark:text-primary-light mb-2"
            for="name"
            >Type your beautiful name</label
          >
          <input
            class="
              w-full
              px-5
              py-2
              border border-gray-300
              dark:border-primary-dark
              border-opacity-50
              text-primary-dark
              dark:text-secondary-light
              bg-ternary-light
              dark:bg-ternary-dark
              rounded-md
              shadow-sm
              text-md
            "
            id="name"
            name="name"
            type="text"
            required=""
            placeholder="in here of course :)"
            aria-label="Name"
          />
        </div>
        <div class="mt-6">
          <label
            class="block text-lg text-primary-dark dark:text-primary-light mb-2"
            for="email"
            >Protect your email address</label
          >
          <input
            class="
              w-full
              px-5
              py-2
              border border-gray-300
              dark:border-primary-dark
              border-opacity-50
              text-primary-dark
              dark:text-secondary-light
              bg-ternary-light
              dark:bg-ternary-dark
              rounded-md
              shadow-sm
              text-md
            "
            id="email"
            name="email"
            type="text"
            required=""
            placeholder="but not in here :)"
            aria-label="Email"
          />
        </div>
  
        <div class="mt-6">
          <Button
            title="Submit"
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
            type="submit"
            aria-label="Submit"
          />
        </div>
      </form>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
