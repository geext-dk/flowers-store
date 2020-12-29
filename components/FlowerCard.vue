<template>
  <div class="shop-item-box">
    <div class="shop-item-image"></div>
    <div class="shop-item-information">
      <div class="text-common shop-item-title">{{ flowerTitle }}</div>
      <flower-color-picker class="shop-item-color-dots"></flower-color-picker>
      <div class="shop-item-price-box">
        <div class="shop-item-price">
          <div class="text-common original-price-box">{{ originalPrice }}</div>
          <div class="text-common real-price-box">
            {{ realPrice }} <span class="text-common price-currency">р.</span>
          </div>
        </div>
        <add-to-cart-button
          class="flower-add-to-cart-button"
          :style="{ display: showAddToCartButton ? 'grid' : 'none' }"
          @click="onAddToCart()"
        ></add-to-cart-button>
        <quantity-changer
          class="flower-quantity-changer"
          :quantity-value="quantityValue"
          :style="{ display: showAddToCartButton ? 'none' : 'grid' }"
          @increment-clicked="onIncrementQuantity()"
          @decrement-clicked="onDecrementQuantity()"
        ></quantity-changer>
      </div>
    </div>
  </div>
</template>

<style>
@font-face {
  font-family: 'Gilroy-Regular';
  src: url(Gilroy-Regular.woff2);
}

body {
  font-family: 'Gilroy-Regular';
}

.shop-item-box {
  background-image: url('./Image.png');
  background-repeat: no-repeat;
  background-size: 100% auto;
  display: inline-block;
  border-radius: 20px;
  border-width: 0px;
  border-color: black;
  border-style: solid;
  height: auto;

  box-shadow: 0px 4px 8px rgba(176, 190, 197, 0.24),
    0px 4px 16px 1px rgba(0, 0, 0, 0.1);
}

.shop-item-color-dots {
  margin-left: 16px;
  margin-right: 16px;
  margin-bottom: 16px;
}

.shop-item-image {
  width: 236px;
  height: 200px;
  margin-bottom: 8px;
}

.shop-item-information {
  width: 100%;
}

.shop-item-title {
  font-size: 24px;
  margin-bottom: 16px;
  margin-left: 16px;
  margin-right: 16px;
}

.shop-item-price-box {
  height: 25%;
  display: flex;
  justify-content: space-between;
  margin-left: 16px;
  margin-right: 16px;
  margin-bottom: 24px;
  align-items: flex-end;
}

.original-price-box {
  text-decoration-line: line-through;
  font-size: 16px;
  color: #38353e;
}

.real-price-box {
  color: #eaa3b6;
  font-size: 24px;
  line-height: 130%;
}

.price-currency {
  font-size: 16px;
}
</style>

<script>
import Vue from 'vue'
import AddToCartButton from './AddToCartButton.vue'
import QuantityChanger from './QuantityChanger.vue'
import FlowerColorPicker from './FlowerColorPicker.vue'

export default Vue.extend({
  components: {
    AddToCartButton,
    QuantityChanger,
    FlowerColorPicker,
  },
  data() {
    return {
      flowerTitle: 'Роза',
      originalPrice: 150,
      realPrice: 1000,
      quantityValue: 0,
    }
  },
  computed: {
    showAddToCartButton() {
      return this.quantityValue <= 0
    },
  },
  methods: {
    onAddToCart() {
      this.onIncrementQuantity()
    },
    onIncrementQuantity() {
      this.quantityValue += 1
    },
    onDecrementQuantity() {
      this.quantityValue -= 1
    },
  },
})
</script>
