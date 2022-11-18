<script setup>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
</script>

<template>
  <Header />
  <Main />
</template>

<style scoped>
.bg-img {
  display: none;
}
@media (min-width: 920px) {
  .container {
    position: relative;
  }

  .hero {
    height: 600px;
  }
  .bg-img {
    display: block;
    position: absolute;
    top: -130px;
    right: 5px;
    z-index: -999;
  }

  .bg-img img {
    height: 700px;
    width: 100%;
  }
}
</style>
