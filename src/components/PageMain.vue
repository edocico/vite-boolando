<script>
import ProductBox from "./ProductBox.vue";

import { store } from "../store";
import axios from "axios";

export default {
  components: {
    ProductBox,
  },
  data() {
    return {
      store,
      modalOpen: false,
      modalProduct: {},
    };
  },
  methods: {
    showModal(product) {
      this.modalOpen = true;

      this.modalProduct = product;
    },
    closeModal() {
      this.modalOpen = false;
      this.modalProduct = {};
    },
    favorites() {
      this.modalProduct.isInFavorites = !this.modalProduct.isInFavorites;
    },
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
          <ProductBox
            v-for="product in store.products"
            :item="product"
            @show="showModal"
          />
        </div>
      </div>
    </section>

    <div class="modal" v-if="modalOpen">
      <div class="card">
        <div class="card-header">
          <p>{{ modalProduct.name }}</p>
          <span class="cross"
            ><font-awesome-icon
              @click="closeModal"
              icon="fa-regular fa-circle-xmark"
          /></span>
        </div>
        <div class="card-body">
          <div class="col-6">
            <img :src="'/img/' + modalProduct.frontImage" alt="" />
          </div>
          <div class="col-6 desc">
            <ul>
              <li><span class="tag">Marca:</span> {{ modalProduct.brand }}</li>
              <li><span class="tag">Modello:</span> {{ modalProduct.name }}</li>
              <li>
                <span class="tag">Prezzo:</span> {{ modalProduct.price }} &euro;
              </li>
              <button class="add" @click="favorites">Aggiungi/Rimuovi</button>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  position: relative;
}
.modal .card {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 5;
  background-color: white;
  border-radius: 30px;
  width: 100%;
  max-width: 400px;
  min-height: 300px;
  box-shadow: 0px 3px 5px black;

  .card-header {
    color: white;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #ff6901;
    padding: 20px;
    border-top-left-radius: 30px;
    border-top-right-radius: 30px;
  }
  .card-header p {
    text-transform: uppercase;
  }

  .card-header span {
    font-size: 20px;
  }

  .card-body {
    display: flex;
    flex-wrap: nowrap;
    justify-content: space-between;

    .col-6 {
      flex-basis: calc(100 / 2);
      padding: 10px;
    }

    img {
      display: block;
      max-width: 200px;
    }

    .tag {
      font-weight: 900;
    }

    .desc {
      display: flex;
      justify-content: flex-start;
      flex-grow: 1;
    }

    .desc li {
      margin-bottom: 20px;
    }

    .add {
      padding: 8px;
      margin-top: 100px;
      border-radius: 10px;
      background-color: #ff6901;
      color: white;
      font-weight: 900;
    }
  }
}
</style>
