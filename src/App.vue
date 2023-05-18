<template>
  <div id="app">
    <header>
      <navbar-header />
    </header>
    <product-pictures-dialog :selected-picture="clickedPictureId" />
    <main>
      <product-pictures @picture-clicked="handlePictureClick" />
      <div class="flex-group">
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
import ProductPicturesDialog from "./components/ProductPicturesDialog.vue"

export default {
  name: "App",
  components: {
    NavbarHeader,
    ProductPictures,
    ProductInfo,
    ActionButtons,
    ProductPicturesDialog
  },
  props: { 
    selectedPicture: {
      type: Number,
      required: false
    }
  },
  watch: {
    clickedPictureId(newValue) {
      this.clickedPictureId = newValue;
      if(this.clickedPictureId) {
        document.querySelector('dialog').showModal();
      }
    }
  },
  data() {
    return {
      clickedPictureId: this.selectedPicture
    }
  },
  methods: {
    handlePictureClick(pictureId) {
      this.clickedPictureId = pictureId;
    }
  }
};
</script>

<style scoped>
header {
  padding-inline: 10rem;
}

@media(min-width: 720px) {
  header {
    padding-inline: 4rem;
  }
}

main {
  margin-block: 3rem;
  display: grid;
  grid-template-columns: 31rem 31rem;
  gap: 9rem;
  justify-content: center;
}

.flex-group {
  display: flex;
  flex-direction: column;
  gap: 3rem;
  justify-content: center;
}
</style>
