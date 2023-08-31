<script>
import feather from "feather-icons";

export default {
  scrollToTop: true,
  data: () => {
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
  <div
    class="
      container
      mx-auto
      flex flex-col-reverse
      md:flex-row md:py-10 md:mt-20
    "
  >
    <div class="w-full md:w-1/2"></div>
    
    <!-- Contact form -->
    <ContactForm />
  </div>
</template>
