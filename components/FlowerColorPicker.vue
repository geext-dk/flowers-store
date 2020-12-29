<template>
  <div class="flower-color-picker">
    <svg
      aria-hidden="true"
      style="position: absolute; width: 0; height: 0; overflow: hidden"
      version="1.1"
      xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink"
    >
      <defs>
        <symbol id="icon-arrow-down-btn" viewBox="0 0 32 32">
          <path
            d="M15.394 18.061l-5.394-5.394c-0.368-0.368-0.965-0.368-1.333 0s-0.368 0.965 0 1.333l6 6c0.736 0.736 1.93 0.736 2.667 0l6-6c0.368-0.368 0.368-0.965 0-1.333s-0.965-0.368-1.333 0l-5.394 5.394c-0.335 0.335-0.877 0.335-1.212 0z"
          ></path>
        </symbol>
      </defs>
    </svg>
    <div class="flower-color-picker-grid">
      <div v-for="color in colorsDisplay" :key="color.id" class="color-dot-box">
        <div class="color-dot"></div>
      </div>
    </div>
    <text-button v-if="!fitsInOneLine" @click="onShowAllColorsClicked()">
      <div class="show-more-colors-btn-content">
        {{ showAllColors ? 'скрыть все цвета' : 'показать все цвета' }}
        <svg class="icon-arrow-down-btn" role="presentation">
          <use xlink:href="#icon-arrow-down-btn" />
        </svg>
      </div>
    </text-button>
  </div>
</template>

<style>
.flower-color-picker-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, 32px);
  grid-template-rows: repeat(auto-fill, 32px);
  justify-content: space-between;
  row-gap: 2px;
}

.icon-arrow-down-btn {
  width: 24px;
  height: 24px;
}

.show-more-colors-btn-content {
  all: unset;
  margin-top: 8px;
  display: flex;
  align-content: center;
  align-items: center;
  cursor: pointer;
}

.color-dot-box {
  width: 32px;
  height: 32px;
  display: flex;
}

.color-dot {
  margin: auto;
  width: 24px;
  height: 24px;
  border-radius: 100%;
  background-color: #c4c4c4;
  display: inline-block;
}
</style>

<script>
import TextButton from './TextButton.vue'

export default {
  components: {
    TextButton,
  },
  data() {
    return {
      colors: Array.from(new Array(11).keys()).map((elem) => {
        return {
          id: elem,
        }
      }),
      showAllColors: false,
    }
  },

  computed: {
    fitsInOneLine() {
      return this.colors.length <= 6
    },
    colorsSingleLine() {
      return this.fitsInOneLine ? this.colors : this.colors.slice(0, 6)
    },
    colorsDisplay() {
      return this.showAllColors ? this.colors : this.colorsSingleLine
    },
  },
  methods: {
    onShowAllColorsClicked() {
      this.showAllColors = !this.showAllColors
    },
  },
}
</script>
