<template>
  <div class="action-buttons">
    <quantity-picker />
    <buy-button />
  </div>
</template>

<script>
import QuantityPicker from "./QuantityPicker.vue";
import BuyButton from "./BuyButton.vue";

export default {
  name: "ActionButtons",
  components: { QuantityPicker, BuyButton },
};
</script>

<style scoped>
.action-buttons {
  display: grid;
  grid-template-columns: 3fr 5fr .1fr;
  grid-template-rows: 4rem;
  gap: 1.5rem;
}
</style>