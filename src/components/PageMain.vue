<script>
import ProductBox from "./ProductBox.vue";
import ProductsJson from "../db.json";
export default {
  components: {
    ProductBox,
  },
  data() {
    return {
      Products: ProductsJson,
    };
  },
};
</script>

<template>
  <main>
    <section class="product">
      <div class="container">
        <div class="row">
          <ProductBox />
        </div>
      </div>
    </section>
  </main>
</template>

<style lang="scss" scoped></style>
