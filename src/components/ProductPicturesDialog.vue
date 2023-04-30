<template>
    <dialog class="product-pictures-dialog">
        <button @click="handleCloseClick">
            <svg width="14" height="15" xmlns="http://www.w3.org/2000/svg">
                <path
                    d="m11.596.782 2.122 2.122L9.12 7.499l4.597 4.597-2.122 2.122L7 9.62l-4.595 4.597-2.122-2.122L4.878 7.5.282 2.904 2.404.782l4.595 4.596L11.596.782Z"
                    fill-rule="evenodd" />
            </svg>
        </button>
        <product-pictures class="dialog-content" />
    </dialog>
</template>

<script>
import ProductPictures from './ProductPictures.vue'

export default {
    components: { ProductPictures },
    methods: {
        handleCloseClick() {
            document.querySelector('dialog').close();
        }
    }
}
</script>

<style scoped>
.product-pictures-dialog {
    width: 31rem;
    overflow: visible;
    border: 0;
    background-color: transparent;
    left: 25%;
    right: 25%;
    top: 25%;
    margin: auto;
    text-align: right;
    position: absolute;
}

.product-pictures-dialog::backdrop {
    background: rgba(0, 0, 0, 0.7)
}

button {
    background-color: transparent;
    border: 0;
    padding: 0;
    margin-block: 1rem;
}

button:hover {
    cursor: pointer;
}

svg {
    fill: var(--color-orange);
}
</style>