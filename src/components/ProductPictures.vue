<template>
  <div class="product-pictures">
    <img class="selected-image" :src="selectedImage" alt="product-image" />
    <div class="thumbnails">
      <button v-for="thumbnail in thumbnails" :key="thumbnail.id" :class="`thumbnail-button ${selectedThumbnail === thumbnail.id ? 'selected' : 'not-selected'
        }`" @click="handleThumbnailClick(thumbnail.id)">
        <img :src="thumbnail.src" class="thumbnail" alt="product-thumbnail" />
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductPictures",
  data() {
    return {
      selectedThumbnail: 1,
      thumbnails: [
        { id: 1, src: "./images/image-product-1-thumbnail.jpg" },
        { id: 2, src: "./images/image-product-2-thumbnail.jpg" },
        { id: 3, src: "./images/image-product-3-thumbnail.jpg" },
        { id: 4, src: "./images/image-product-4-thumbnail.jpg" },
      ],
    };
  },
  computed: {
    selectedImage() {
      return `./images/image-product-${this.selectedThumbnail}.jpg`;
    },
  },
  methods: {
    handleThumbnailClick(thumbnailId) {
      this.selectedThumbnail = thumbnailId;
      document.querySelector('dialog').showModal();
    }
  }
};
</script>

<style>
.product-pictures {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 2rem;
}

.selected-image {
  width: 100%;
  border-radius: 1rem;
}

.thumbnails {
  display: flex;
  gap: 2rem;
  --thumbnail-width: calc((31rem - (2rem * 3)) / 4);
}

.thumbnail {
  border-radius: 1rem;
  margin: 0;
  border: 0;
  width: 100%;
  height: auto;
}

.thumbnail-button {
  border: 0;
  margin: 0;
  padding: 0;
  border-radius: 1rem;
  width: var(--thumbnail-width);
  height: var(--thumbnail-width);
}

.not-selected:hover {
  opacity: .5;
  cursor: pointer;
}

.selected {
  --border-size: 2px;
  --max-size: calc(var(--thumbnail-width) - var(--border-size));
  border-radius: calc(1rem + var(--border-size));
  border: var(--border-size) solid var(--color-orange);
  max-width: var(--max-size);
  max-height: var(--max-size);
}

.selected img {
  opacity: .3;
}
</style>