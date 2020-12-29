<template>
  <button class="quantity-changer">
    <svg
      aria-hidden="true"
      style="position: absolute; width: 0; height: 0; overflow: hidden"
      version="1.1"
      xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink"
    >
      <defs>
        <symbol id="icon-minus-quantity-active" viewBox="0 0 32 32">
          <path
            fill="#5297d7"
            style="fill: var(--color1, #5297d7)"
            d="M16 0c8.837 0 16 7.163 16 16s-7.163 16-16 16c-8.837 0-16-7.163-16-16s7.163-16 16-16z"
          ></path>
          <path
            fill="#fff"
            style="fill: var(--color2, #fff)"
            d="M8 15.5c0-0.828 0.672-1.5 1.5-1.5h12c0.828 0 1.5 0.672 1.5 1.5s-0.672 1.5-1.5 1.5h-12c-0.828 0-1.5-0.672-1.5-1.5z"
          ></path>
        </symbol>
        <symbol id="icon-minus-quantity-hover" viewBox="0 0 32 32">
          <path
            fill="#a3c8ea"
            style="fill: var(--color3, #a3c8ea)"
            d="M16 0c8.837 0 16 7.163 16 16s-7.163 16-16 16c-8.837 0-16-7.163-16-16s7.163-16 16-16z"
          ></path>
          <path
            fill="#fff"
            style="fill: var(--color2, #fff)"
            d="M8 15.5c0-0.828 0.672-1.5 1.5-1.5h12c0.828 0 1.5 0.672 1.5 1.5s-0.672 1.5-1.5 1.5h-12c-0.828 0-1.5-0.672-1.5-1.5z"
          ></path>
        </symbol>
        <symbol id="icon-plus-quantity-active" viewBox="0 0 32 32">
          <path
            fill="#5297d7"
            style="fill: var(--color1, #5297d7)"
            d="M16 0c8.837 0 16 7.163 16 16s-7.163 16-16 16c-8.837 0-16-7.163-16-16s7.163-16 16-16z"
          ></path>
          <path
            fill="#fff"
            style="fill: var(--color2, #fff)"
            d="M17.177 9.5c0-0.828-0.672-1.5-1.5-1.5s-1.5 0.672-1.5 1.5v4.323h-4.677c-0.828 0-1.5 0.672-1.5 1.5s0.672 1.5 1.5 1.5h4.677v4.677c0 0.828 0.671 1.5 1.5 1.5s1.5-0.672 1.5-1.5v-4.677h4.323c0.828 0 1.5-0.671 1.5-1.5s-0.672-1.5-1.5-1.5h-4.323v-4.323z"
          ></path>
        </symbol>
        <symbol id="icon-plus-quantity-hover" viewBox="0 0 32 32">
          <path
            fill="#a3c8ea"
            style="fill: var(--color3, #a3c8ea)"
            d="M16 0c8.837 0 16 7.163 16 16s-7.163 16-16 16c-8.837 0-16-7.163-16-16s7.163-16 16-16z"
          ></path>
          <path
            fill="#fff"
            style="fill: var(--color2, #fff)"
            d="M17.177 9.5c0-0.828-0.672-1.5-1.5-1.5s-1.5 0.672-1.5 1.5v4.323h-4.677c-0.828 0-1.5 0.672-1.5 1.5s0.672 1.5 1.5 1.5h4.677v4.677c0 0.828 0.671 1.5 1.5 1.5s1.5-0.672 1.5-1.5v-4.677h4.323c0.828 0 1.5-0.671 1.5-1.5s-0.672-1.5-1.5-1.5h-4.323v-4.323z"
          ></path>
        </symbol>
        <symbol id="icon-minus-quantity" viewBox="0 0 32 32">
          <path
            fill="#a3c8ea"
            style="fill: var(--color3, #a3c8ea)"
            d="M8 15.5c0-0.828 0.672-1.5 1.5-1.5h12c0.828 0 1.5 0.672 1.5 1.5s-0.672 1.5-1.5 1.5h-12c-0.828 0-1.5-0.672-1.5-1.5z"
          ></path>
          <path
            fill="none"
            stroke="#a3c8ea"
            style="stroke: var(--color3, #a3c8ea)"
            stroke-linejoin="miter"
            stroke-linecap="butt"
            stroke-miterlimit="4"
            stroke-width="4"
            d="M16 2c7.732 0 14 6.268 14 14s-6.268 14-14 14c-7.732 0-14-6.268-14-14s6.268-14 14-14z"
          ></path>
        </symbol>
        <symbol id="icon-plus-quantity" viewBox="0 0 32 32">
          <path
            fill="#a3c8ea"
            style="fill: var(--color3, #a3c8ea)"
            d="M17.177 9.5c0-0.828-0.672-1.5-1.5-1.5s-1.5 0.672-1.5 1.5v4.323h-4.677c-0.828 0-1.5 0.672-1.5 1.5s0.672 1.5 1.5 1.5h4.677v4.677c0 0.828 0.671 1.5 1.5 1.5s1.5-0.672 1.5-1.5v-4.677h4.323c0.828 0 1.5-0.671 1.5-1.5s-0.672-1.5-1.5-1.5h-4.323v-4.323z"
          ></path>
          <path
            fill="none"
            stroke="#a3c8ea"
            style="stroke: var(--color3, #a3c8ea)"
            stroke-linejoin="miter"
            stroke-linecap="butt"
            stroke-miterlimit="4"
            stroke-width="4"
            d="M16 2c7.732 0 14 6.268 14 14s-6.268 14-14 14c-7.732 0-14-6.268-14-14s6.268-14 14-14z"
          ></path>
        </symbol>
      </defs>
    </svg>
    <div class="quantity-minus" @click="minusQuantity()">
      <svg class="quantity-minus-normal" role="img" title="Minus quantity">
        <use xlink:href="#icon-minus-quantity" />
      </svg>
      <svg class="quantity-minus-hover" role="img" title="Minus quantity">
        <use xlink:href="#icon-minus-quantity-hover" />
      </svg>
      <svg class="quantity-minus-active" role="img" title="Minus quantity">
        <use xlink:href="#icon-minus-quantity-active" />
      </svg>
    </div>
    <div class="quantity-value">{{ quantityValue }}</div>
    <div class="quantity-plus" @click="plusQuantity()">
      <svg class="quantity-plus-normal" role="img" title="Plus quantity">
        <use xlink:href="#icon-plus-quantity" />
      </svg>
      <svg class="quantity-plus-hover" role="img" title="Plus quantity">
        <use xlink:href="#icon-plus-quantity-hover" />
      </svg>
      <svg class="quantity-plus-active" role="img" title="Plus quantity">
        <use xlink:href="#icon-plus-quantity-active" />
      </svg>
    </div>
  </button>
</template>

<style lang="scss">
@font-face {
  font-family: 'Gilroy-Regular';
  src: url(Gilroy-Regular.woff2);
}

body {
  font-family: 'Gilroy-Regular';
}
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

<script>
import Vue from 'vue'

export default Vue.extend({
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
})
</script>
