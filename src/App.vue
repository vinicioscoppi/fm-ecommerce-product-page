<template>
  <div id="app">
  <header>
    <navbar-header></navbar-header>
  </header>
    <main>
      <product-showcase></product-showcase>
      <product-info></product-info>
    </main>

    Sneaker Company Fall Limited Edition Sneakers These low-profile sneakers are
    your perfect casual wear companion. Featuring a durable rubber outer sole,
    they’ll withstand everything the weather can offer. $125.00 50% $250.00 0
    Add to cart
  </div>
</template>

<script>
import NavbarHeader from "./components/NavbarHeader.vue";

export default {
  name: "App",
  components: {
    NavbarHeader,
  },
};
</script>

<style>
#app {
  font-size: 16px;
  font-family: "Kumbh Sans", sans-serif;
  padding: 0 10rem;
  min-height: 100vh;
}
</style>
