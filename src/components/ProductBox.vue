<script>
export default {
  data() {
    return {};
  },
  methods: {},
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
};
</script>

<template>
  <div class="product-box">
    <div class="product-display">
      <img
        class="product-image-a"
        :src="'/img/' + item.frontImage"
        alt="levi's shirt1"
      />
      <!--immagine B-->
      <img class="product-image-b" :src="'/img/' + item.backImage" alt="1b" />
      <span class="heart" :class="item.isInFavorites ? 'favorites' : ''"
        >&hearts;</span
      >
      <span :class="badge.type" v-for="(badge, index) in item.badges">
        {{ badge.value }}</span
      >
      <!-- <span class="red-label">-50%</span>
      <span class="green-label">Sostenibilità</span> -->
    </div>
    <div class="product-info" @click="$emit('show')">
      <span class="brand">{{ item.brand }}</span>
      <span class="pruduct-title">{{ item.name }}</span>
      <span class="pricetag">14,99 &euro;</span>
      <span class="discount">{{ item.price }} &euro;</span>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.product-box {
  flex-basis: calc(100% / 3);
  padding: 25px 10px;
}

.favorites {
  color: red;
}

.product-display {
  position: relative;
}

.heart {
  display: block;
  position: absolute;
  top: 10px;
  right: 0px;
  font-size: 20px;
  background-color: white;
  padding: 10px;
}

.heart:hover {
  color: red;
}

.discount {
  display: block;
  position: absolute;
  background-color: red;
  left: 0px;
  bottom: 40px;
  color: white;
  font-size: 14px;
  line-height: 1.5em;
  padding: 0 5px;
}

.tag {
  display: block;
  position: absolute;
  background-color: green;
  color: white;
  font-size: 14px;
  line-height: 1.5em;
  padding: 0 5px;
  bottom: 40px;
  left: 43px;
}

.green-label-only {
  left: 0px;
  display: block;
  position: absolute;
  background-color: green;
  color: white;
  font-size: 14px;
  line-height: 1.5em;
  padding: 0 5px;
  bottom: 40px;
}

.product-info {
  position: relative;
}

.brand {
  display: block;
  font-size: 14px;
}

.pruduct-title {
  display: block;
  font-weight: 600;
}

.pricetag {
  color: red;
}

.discount {
  text-decoration: line-through;
}

.product-image-b {
  display: none;
}

.product-display:hover .product-image-b {
  display: block;
  position: absolute;
  top: 0px;
  bottom: 0px;
  left: 0px;
  right: 0px;
}
</style>
