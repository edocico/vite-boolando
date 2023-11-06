<script>
import ProductBox from "./ProductBox.vue";
export default {
  components: {
    ProductBox,
  },
  data() {
    return {};
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
