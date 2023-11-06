<script>
export default {
  data() {
    return;
  },
};
</script>

<template>
  <div class="product-box">
    <div class="product-display">
      <img class="product-image-a" src="/img/1.webp" alt="levi's shirt1" />
      <!--immagine B-->
      <img class="product-image-b" src="/img/1b.webp" alt="1b" />
      <span class="heart">&hearts;</span>
      <span class="red-label">-50%</span>
      <span class="green-label">Sostenibilità</span>
    </div>
    <div class="product-info">
      <span class="brand">Levi's</span>
      <span class="pruduct-title">RELAXED FIT TEE UNISEX</span>
      <span class="pricetag">14,99 &euro;</span>
      <span class="discount">29,99 &euro;</span>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.product-box {
  flex-basis: calc(100% / 3);
  padding: 25px 10px;
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

.red-label {
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

.green-label {
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
