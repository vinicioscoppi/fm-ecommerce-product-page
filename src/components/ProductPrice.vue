<template>
  <div class="product-price">
    <div class="flex-group">
      <span class="current">${{ current }}.00</span>
      <span class="off">{{ off }}%</span>
    </div>
    <span class="original">
      ${{ original }}.00
    </span>
  </div>
</template>

<script>
export default {
  name: "ProductPrice",
  props: {
    current: {
      type: Number,
      required: true,
    },
    original: {
      type: Number,
      required: true,
    },
    off: {
      type: Number,
      required: true,
    },
  },
};
</script>

<style scoped>
.product-price {
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
}

.flex-group {
  display: flex;
  gap: 1.2rem;
  align-items: center;
}

.current {
  font-weight: 700;
  color: var(--color-black);
  font-size: 2rem;
}

.off {
  color: var(--color-orange);
  background-color: var(--color-pale-orange);
  font-weight: 700;
  font-size: 1.2rem;
  padding: .2rem .5rem;
  border-radius: .25rem;
}

.original {
  font-weight: 700;
  color: var(--color-grayish-blue);
  font-size: 1.1rem;
  text-decoration: line-through;
}
</style>