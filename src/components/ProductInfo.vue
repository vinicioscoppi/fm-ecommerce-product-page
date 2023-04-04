<template>
  <div class="product-info">
    <h2>Sneaker Company</h2>
    <h1>Fall Limited Edition Sneakers</h1>
    <p>
      These low-profile sneakers are your perfect casual wear companion.
      Featuring a durable rubber outer sole, they’ll withstand everything the
      weather can offer.
    </p>
    <product-price :current="125" :original="250" :off="50" />
  </div>
</template>

<script>
import ProductPrice from "./ProductPrice.vue";

export default {
  name: "ProductInfo",
  components: {
    ProductPrice,
  },
};
</script>

<style scoped>
.product-info {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  
}

h1 {
  font-size: 3rem;
  color: var(--color-black);
  font-weight: 700;
  letter-spacing: .05rem;
  line-height: 1;
  
}

h2 {
  color: var(--color-orange);
  font-size: 1rem;
  text-transform: uppercase;
  font-weight: 700;
  letter-spacing: .1rem;
}

p {
  letter-spacing: .06rem;
  font-weight: 400;
  line-height: 1.6;
}
</style>