<script>
import { mapState } from "vuex";
import feather from "feather-icons";

export default {
  data: () => {
    return {
      selectedProduct: "",
      searchProduct: "",
    };
  },
  computed: {
    ...mapState(["productsHeading", "productsDescription", "products"]),
    filteredProducts() {
      if (this.selectedProduct) {
        return this.filterProductsByCategory();
      } else if (this.searchProduct) {
        return this.filterProductsBySearch();
      }
      return this.products;
    },
  },
  methods: {
    filterProductsByCategory() {
      return this.products.filter((item) => {
        let category =
          item.category.charAt(0).toUpperCase() + item.category.slice(1);
        return category.includes(this.selectedProduct);
      });
    },
    filterProductsBySearch() {
      let product = new RegExp(this.searchProduct, "i");
      return this.products.filter((el) => el.title.match(product));
    },
  },
  mounted() {
    feather.replace();
  },
};
</script>

<template>
  <div class="pt-10 sm:pt-20 md:pt-24 mb-10">
    <!-- Product grid header -->
    <div class="text-center">
      <p
        class="
          flex 
          justify-center
          items-center
          font-general-semibold
          text-2xl
          sm:text-5xl
          font-semibold
          mb-2
          text-ternary-dark
          dark:text-ternary-light
        "
      >
        {{ productsHeading }} 
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="currentColor w-12 h-12"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z"
            />
          </svg>
      </p>
    </div>

    <!-- Filter and search products -->
    <div class="mt-8 sm:mt-10">
      <h3
        class="
          font-general-regular
          text-center text-secondary-dark
          dark:text-ternary-light
          text-md
          sm:text-xl
          font-normal
          mb-4
        "
      >
        Search product by title or filter by category
      </h3>
      <div
        class="
          flex
          justify-between
          border-b border-primary-light
          dark:border-secondary-dark
          pb-3
          gap-2
        "
      >
        <div class="flex justify-between gap-2">
          <span
            class="
              hidden
              sm:block
              bg-primary-light
              dark:bg-ternary-dark
              p-2.5
              shadow-sm
              rounded-xl
              cursor-pointer
            "
          >
            <i
              data-feather="search"
              class="text-ternary-dark dark:text-ternary-light"
            ></i>
          </span>
          <input
            v-model="searchProduct"
            class="
              font-general-medium
              pl-3
              pr-1
              sm:px-4
              py-2
              border-1 border-gray-200
              dark:border-secondary-dark
              rounded-lg
              text-sm
              sm:text-md
              bg-secondary-light
              dark:bg-ternary-dark
              text-primary-dark
              dark:text-ternary-light
            "
            id="name"
            name="name"
            type="search"
            required=""
            placeholder="Search Products"
            aria-label="Name"
          />
        </div>
        <ProductsFilter @change="selectedProduct = $event" />
      </div>
    </div>

    <!-- Products grid -->
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 mt-6 sm:gap-10">
      <div
        v-for="product in filteredProducts"
        :key="product.id"
        class="
          rounded-xl
          shadow-lg
          hover:shadow-xl
          cursor-pointer
          mb-10
          sm:mb-0
          bg-secondary-light
          dark:bg-ternary-dark
        "
        aria-label="Single Product"
      >
          <div>
            <img
              :src="product.img"
              :alt="product.title"
              class="rounded-t-xl border-none"
            />
          </div>
          <div class="text-center px-4 py-6">
            <p
              class="
                font-general-semibold
                text-xl text-ternary-dark
                dark:text-ternary-light
                font-semibold
                mb-2
              "
            >
              {{ product.title }}
            </p>
            <span
              class="
                font-general-medium
                text-lg text-ternary-dark
                dark:text-ternary-light
              "
              >{{ product.category }}</span
            >
          </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
