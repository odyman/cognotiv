<template>
  <div
    class="bg-secondary-light dark:bg-primary-dark min-h-screen flex flex-col"
  >
    <!-- App header -->
    <AppHeader />

    <!-- Render contents with transition -->
    <transition name="fade" mode="out-in">
      <Nuxt />
    </transition>

  </div>
</template>

<script>
import feather from "feather-icons";
import AppHeader from "../components/shared/AppHeader.vue";
export default {
  data: () => {
    return {
      // Todo
    };
  },
  mounted() {
    feather.replace();
  },
  components: { AppHeader },
};
</script>

<style>
.fade-enter-active {
  animation: coming 0.4s;
  animation-delay: 0.2s;
  opacity: 0;
}

.fade-leave-active {
  animation: going 0.4s;
}

@keyframes going {
  from {
    transform: translateX(0);
  }

  to {
    transform: translateX(-10px);
    opacity: 0;
  }
}

@keyframes coming {
  from {
    transform: translateX(-10px);
    opacity: 0;
  }

  to {
    transform: translateX(0px);
    opacity: 1;
  }
}
</style>
