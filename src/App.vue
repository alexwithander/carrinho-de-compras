<template>
  <div class="app">
    <CarrinhodeCompras> </CarrinhodeCompras>
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
