<template>
  <div class="app">
    <CarrinhodeCompras/>
  </div>
  <div class="text-center mt-5">
      <p>by alexander</p>
  </div>
</template>

<script>
import CarrinhodeCompras from "./components/CarrinhodeCompras.vue";

export default {
  name: "App",
  components: {
    CarrinhodeCompras,
  },
};
</script>

<style>
@import '~bootstrap/dist/css/bootstrap.css';
</style>
