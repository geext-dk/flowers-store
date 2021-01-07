<template>
  <div class="shopping-cart-btn">
    <icon-shopping-cart class="shopping-cart-icon" />
    <div class="shopping-cart-hover-active"></div>
    <div class="shopping-cart-items-count">
      {{ itemsAmount }}
    </div>
  </div>
</template>

<script>
import IconShoppingCart from './icons/IconShoppingCart.vue'
export default {
  components: {
    IconShoppingCart,
  },
  props: {
    itemsAmount: {
      type: Number,
      required: true,
    },
  },
}
</script>

<style scoped>
.shopping-cart-btn {
  width: 50px;
  height: 70px;
  position: relative;
  cursor: pointer;
}

.shopping-cart-items-count {
  position: absolute;
  left: 23px;
  top: 3px;
  padding: 3px 4px 0px;
  height: 24px;
  background-color: #2566a1;
  border: 0px solid #2566a1;
  color: #ffffff;
  border-radius: 50px;
  text-align: center;
  line-height: 24px;
  font-weight: bold;
  user-select: none;
}

.shopping-cart-btn .shopping-cart-icon {
  position: absolute;
  height: 20px;
  width: 20px;
  left: calc(50% - 20px / 2 - 1px);
  top: calc(50% - 20px / 2);
}

.shopping-cart-hover-active {
  display: none;
  width: 39px;
  height: 39px;
  position: absolute;
  left: calc(50% - 39px / 2 - 0.5px);
  top: calc(50% - 39px / 2 - 0.5px);
  border: 2px solid #2566a1;
  border-radius: 20px;
  text-align: center;
  z-index: -1;
}

.shopping-cart-btn:hover .shopping-cart-hover-active {
  display: block;
  border-color: #5297d7;
}

.shopping-cart-btn:active .shopping-cart-hover-active {
  display: block;
  border-color: #2566a1;
}
</style>
