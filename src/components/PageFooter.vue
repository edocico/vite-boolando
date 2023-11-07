<script>
export default {
  data() {
    return {};
  },
};
</script>

<template>
  <footer>
    <section>
      <div class="container">
        <div class="row">
          <div class="col-6">
            <p>Boolando s.r.l</p>
            <ul class="left-list">
              <li><a href="#">Informazioni legali</a></li>
              <li><a href="#">Informativa sulla privacy</a></li>
              <li><a href="#">Diritto di recesso</a></li>
            </ul>
          </div>
          <div class="col-6">
            <p>Trovaci anche su</p>
            <ul>
              <li>&hearts;</li>
              <li>&hearts;</li>
              <li>&hearts;</li>
              <li>&hearts;</li>
              <li>&hearts;</li>
            </ul>
          </div>
        </div>
      </div>
    </section>
  </footer>
</template>

<style lang="scss" scoped>
footer section {
  min-height: 60px;
  background-color: #1a1a1a;
  width: 100%;
}

.col-6 {
  flex-basis: calc(100% / 2);
}

.col-6 a {
  text-decoration: none;
  color: white;
  padding-left: 3px;
}

.col-6 p {
  color: white;
  font-size: 16px;
  font-weight: 700;
  padding-top: 10px;
  padding-bottom: 10px;
}

.col-6 li {
  color: white;
  padding-left: 3px;
}

footer .row {
  justify-content: space-between;
}

.left-lift {
  display: flex;
  flex-direction: row;
}
</style>
