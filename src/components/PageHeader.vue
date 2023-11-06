<script>
export default {
  data() {
    return {};
  },
};
</script>

<template>
  <header>
    <section>
      <div class="container">
        <div class="row">
          <div class="col-4">
            <ul>
              <li><a href="#">Donna</a></li>
              <li><a href="#">Uomo</a></li>
              <li><a href="#">Bambini</a></li>
            </ul>
          </div>
          <div class="col-4">
            <img class="logo" src="/img/boolean-logo.png" alt="logo" />
          </div>
          <div class="col-4">
            <span>placeholder</span>
          </div>
        </div>
      </div>
    </section>
  </header>
</template>

<style lang="scss" scoped>
header {
  background-color: #ff6901;
  position: sticky;
  width: 100%;
  top: 0;
  left: 0;
  z-index: 999;
}

header .container {
  min-height: 40px;
}

ul {
  list-style: none;
  display: flex;
}

.col-4 li {
  padding-top: 10px;
  padding-left: 5px;
}

.col-4 a {
  text-decoration: none;
  color: white;
}

.col-4 img {
  width: 150px;
  display: block;
}

.col-4 {
  flex-basis: calc(100% / 3);
}

.container {
  max-width: 1000px;
  margin: 0 auto;
}

.row {
  display: flex;
  flex-flow: row wrap;
}
</style>
