<template>
  <div class="quantity-picker">
    <button class="minus" @click="quantity--" :disabled="quantity <= 0">
      <svg width="12" height="4" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
        <defs>
          <path
            d="M11.357 3.332A.641.641 0 0 0 12 2.69V.643A.641.641 0 0 0 11.357 0H.643A.641.641 0 0 0 0 .643v2.046c0 .357.287.643.643.643h10.714Z"
            id="a" />
        </defs>
        <use fill-rule="nonzero" xlink:href="#a" />
      </svg>
    </button>
    {{ quantity }}
    <button class="plus" @click="quantity++" :disabled="quantity >= 10">
      <svg width="12" height="12" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
        <defs>
          <path
            d="M12 7.023V4.977a.641.641 0 0 0-.643-.643h-3.69V.643A.641.641 0 0 0 7.022 0H4.977a.641.641 0 0 0-.643.643v3.69H.643A.641.641 0 0 0 0 4.978v2.046c0 .356.287.643.643.643h3.69v3.691c0 .356.288.643.644.643h2.046a.641.641 0 0 0 .643-.643v-3.69h3.691A.641.641 0 0 0 12 7.022Z"
            id="b" />
        </defs>
        <use fill-rule="nonzero" xlink:href="#b" />
      </svg>
    </button>
  </div>
</template>

<script>
export default {
  name: "QuantityPicker",
  data() {
    return {
      quantity: 0
    }
  }
};
</script>

<style scoped>
.quantity-picker {
  width: 100%;
  max-width: 100%;
  background-color: var(--color-light-grayish-blue);
  border-radius: 0.5rem;
  color: var(--color-black);
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 1.2rem;
  font-weight: 700;
}

button {
  margin: 0;
  padding: 0;
  border: 0;
  background: transparent;
}

svg {
  padding: 1rem;
  fill: var(--color-orange);
}

svg:hover {
  cursor: pointer;
  fill: var(--color-orange-hover);
}
</style>