<script>
import ProductBox from "./ProductBox.vue";
import productsJson from "../db.json";
export default {
  components: {
    ProductBox,
  },
  data() {
    return {
      products: productsJson.products,
    };
  },
  mounted() {
    console.log(this.products);
  },
};
</script>

<template>
  <main>
    <section class="product">
      <div class="container">
        <div class="row">
          <ProductBox v-for="product in products" :item="product" />
        </div>
      </div>
    </section>
  </main>
</template>

<style lang="scss" scoped></style>
