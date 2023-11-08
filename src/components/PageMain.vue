<script>
import ProductBox from "./ProductBox.vue";
//import productsJson from "../db.json";
import { store } from "../store";
import axios from "axios";

export default {
  components: {
    ProductBox,
  },
  data() {
    return {
      //products: productsJson.products,
      // products: store.products,
      store,
    };
  },
  mounted() {
    console.log(this.products);
  },
  created() {
    axios.get("http://localhost:3000/products").then((res) => {
      const item = res.data;
      console.log(res, item);
      this.store.products = item;
    });
  },
};
</script>

<template>
  <main>
    <section class="product">
      <div class="container">
        <div class="row">
          <ProductBox v-for="product in store.products" :item="product" />
        </div>
      </div>
    </section>
  </main>
</template>

<style lang="scss" scoped></style>
