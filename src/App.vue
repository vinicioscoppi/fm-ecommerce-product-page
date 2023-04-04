<template>
  <div id="app">
    <header>
      <navbar-header />
    </header>
    <main>
      <product-pictures />
      <div class="flex-group flex-group-column">
        <product-info />
        <action-buttons />
      </div>
    </main>
  </div>
</template>

<script>
import NavbarHeader from "./components/NavbarHeader.vue";
import ProductPictures from "./components/ProductPictures.vue";
import ProductInfo from "./components/ProductInfo.vue";
import ActionButtons from "./components/ActionButtons.vue"

export default {
  name: "App",
  components: {
    NavbarHeader,
    ProductPictures,
    ProductInfo,
    ActionButtons
  },
};
</script>

<style>
#app {
  padding: 0 10rem;
}

main {
  padding: 3rem 1rem;
  display: grid;
  grid-template-columns: 4rem 31rem 9rem 31rem;
}


.flex-group {
  display: flex;
}

.flex-group-column {
  flex-direction: column;
  gap: 3rem;
  justify-content: center;
  grid-column-start: 4;
}
</style>
