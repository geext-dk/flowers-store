<template>
  <button class="quantity-changer">
    <div class="quantity-minus" @click="minusQuantity()">
      <icon-quantity-minus-normal
        class="quantity-minus-normal"
        role="img"
        title="Minus quantity"
      />
      <icon-quantity-minus-hover
        class="quantity-minus-hover"
        role="img"
        title="Minus quantity"
      />
      <icon-quantity-minus-active
        class="quantity-minus-active"
        role="img"
        title="Minus quantity"
      />
    </div>
    <div class="quantity-value">{{ quantityValue }}</div>
    <div class="quantity-plus" @click="plusQuantity()">
      <icon-quantity-plus-normal
        class="quantity-plus-normal"
        role="img"
        title="Plus quantity"
      />
      <icon-quantity-plus-hover
        class="quantity-plus-hover"
        role="img"
        title="Plus quantity"
      />
      <icon-quantity-plus-active
        class="quantity-plus-active"
        role="img"
        title="Plus quantity"
      />
    </div>
  </button>
</template>

<script>
import IconQuantityMinusNormal from './icons/IconQuantityMinusNormal.vue'
import IconQuantityMinusHover from './icons/IconQuantityMinusHover.vue'
import IconQuantityMinusActive from './icons/IconQuantityMinusActive.vue'
import IconQuantityPlusNormal from './icons/IconQuantityPlusNormal.vue'
import IconQuantityPlusHover from './icons/IconQuantityPlusHover.vue'
import IconQuantityPlusActive from './icons/IconQuantityPlusActive.vue'
export default {
  components: {
    IconQuantityMinusNormal,
    IconQuantityMinusHover,
    IconQuantityMinusActive,
    IconQuantityPlusNormal,
    IconQuantityPlusHover,
    IconQuantityPlusActive,
  },
  props: {
    quantityValue: {
      type: Number,
      default: 0,
    },
  },
  methods: {
    plusQuantity() {
      this.$emit('increment-clicked')
    },

    minusQuantity() {
      this.$emit('decrement-clicked')
    },
  },
}
</script>

<style lang="scss">
.quantity-changer {
  all: unset;
  display: grid;
  width: 96px;
  height: 32px;
  grid-template-columns: auto auto auto;
  justify-content: space-between;
}

.quantity-value {
  display: inline-flex;
  justify-content: center;
  justify-items: center;
  align-items: center;
  font-size: 16px;
}

.quantity-plus {
  width: 32px;
  height: 32px;
  cursor: pointer;

  .quantity-plus-normal {
    display: block;
    width: 32px;
    height: 32px;
  }

  .quantity-plus-hover,
  .quantity-plus-active {
    display: none;
    width: 32px;
    height: 32px;
  }

  &:hover {
    .quantity-plus-hover {
      display: block;
    }

    .quantity-plus-normal {
      display: none;
    }
  }

  &:active {
    .quantity-plus-active {
      display: block;
    }

    .quantity-plus-normal {
      display: none;
    }

    .quantity-plus-hover {
      display: none;
    }
  }
}

.quantity-minus {
  width: 32px;
  height: 32px;
  cursor: pointer;

  .quantity-minus-normal {
    display: block;
    width: 32px;
    height: 32px;
  }

  .quantity-minus-hover,
  .quantity-minus-active {
    display: none;
    width: 32px;
    height: 32px;
  }

  &:hover {
    .quantity-minus-hover {
      display: block;
    }

    .quantity-minus-normal {
      display: none;
    }
  }

  &:active {
    .quantity-minus-active {
      display: block;
    }

    .quantity-minus-normal {
      display: none;
    }

    .quantity-minus-hover {
      display: none;
    }
  }
}
</style>
