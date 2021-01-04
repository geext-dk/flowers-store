<template>
  <div class="shop-item-box">
    <div
      class="shop-item-image"
      :style="{ backgroundImage: `url('${imageUrl}')` }"
    ></div>
    <div class="shop-item-information">
      <div>
        <div class="text-common shop-item-title">{{ title }}</div>
        <flower-color-picker
          :colors="colors"
          class="shop-item-color-dots"
        ></flower-color-picker>
      </div>
      <div class="shop-item-price-box">
        <div class="shop-item-price">
          <div v-if="originalPrice > 0" class="text-common original-price-box">
            {{ originalPrice }}
          </div>
          <div class="text-common real-price-box">
            {{ price }} <span class="text-common price-currency">р.</span>
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

<script>
import AddToCartButton from './AddToCartButton.vue'
import QuantityChanger from './QuantityChanger.vue'
import FlowerColorPicker from './FlowerColorPicker.vue'

export default {
  components: {
    AddToCartButton,
    QuantityChanger,
    FlowerColorPicker,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
    price: {
      type: Number,
      required: true,
    },
    originalPrice: {
      type: Number,
      default: 0,
    },
    imageUrl: {
      type: String,
      required: true,
    },
    colors: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
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
}
</script>

<style>
.shop-item-box {
  background-repeat: no-repeat;
  background-size: 100% auto;
  display: inline-flex;
  flex-direction: column;
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
  width: 224px;
  height: 200px;
  margin-bottom: 8px;
  border-top-left-radius: 20px;
  border-top-right-radius: 20px;
}

.shop-item-information {
  width: 100%;
  display: flex;
  flex-grow: 1;
  flex-direction: column;
  justify-content: space-between;
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
</style>
