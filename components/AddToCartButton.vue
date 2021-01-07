<template>
  <button class="shop-item-add-to-cart" @click="onClick()">
    <icon-add-to-cart-normal
      class="add-to-cart-normal"
      role="img"
      title="AddToCart"
    />
    <icon-add-to-cart-hover
      class="add-to-cart-hover"
      role="img"
      title="AddToCart"
    />
    <icon-add-to-cart-active
      class="add-to-cart-active"
      role="img"
      title="AddToCart"
    />
  </button>
</template>

<script>
import IconAddToCartActive from './icons/IconAddToCartActive.vue'
import IconAddToCartHover from './icons/IconAddToCartHover.vue'
import IconAddToCartNormal from './icons/IconAddToCartNormal.vue'
export default {
  components: {
    IconAddToCartNormal,
    IconAddToCartHover,
    IconAddToCartActive,
  },
  methods: {
    onClick() {
      this.$emit('click')
    },
  },
}
</script>

<style scoped>
.shop-item-add-to-cart {
  all: unset;
  cursor: pointer;
  user-select: none;
}

.shop-item-add-to-cart svg {
  width: 80px;
  height: 48px;
}

.shop-item-add-to-cart .add-to-cart-normal {
  display: block;
}

.shop-item-add-to-cart .add-to-cart-hover {
  display: none;
}

.shop-item-add-to-cart .add-to-cart-active {
  display: none;
}

.shop-item-add-to-cart:hover .add-to-cart-normal {
  display: none;
}

.shop-item-add-to-cart:hover .add-to-cart-hover {
  display: block;
}

.shop-item-add-to-cart:hover .add-to-cart-active {
  display: none;
}

.shop-item-add-to-cart:active .add-to-cart-normal {
  display: none;
}

.shop-item-add-to-cart:active .add-to-cart-hover {
  display: none;
}

.shop-item-add-to-cart:active .add-to-cart-active {
  display: block;
}
</style>
