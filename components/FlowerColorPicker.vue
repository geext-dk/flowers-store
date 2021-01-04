<template>
  <div class="flower-color-picker">
    <div class="flower-color-picker-grid">
      <div
        v-for="(color, index) in colorsDisplay"
        :key="`color-${index}`"
        class="color-dot-box"
      >
        <div :style="{ backgroundColor: color.color }" class="color-dot"></div>
      </div>
    </div>
    <text-button
      v-if="!fitsInOneLine"
      class="show-all-colors-btn"
      @click="onShowAllColorsClicked()"
    >
      {{ showAllColors ? 'скрыть все цвета' : 'показать все цвета' }}
      <template v-slot:icon>
        <icon-arrow-down
          :class="{
            'icon-arrow-down-btn': !showAllColors,
            'icon-arrow-up-btn': showAllColors,
          }"
          role="presentation"
        />
      </template>
    </text-button>
  </div>
</template>

<script>
import TextButton from './TextButton.vue'
import IconArrowDown from './icons/IconArrowDown.vue'

export default {
  components: {
    TextButton,
    IconArrowDown,
  },
  props: {
    colors: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
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

<style>
.flower-color-picker-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, 32px);
  grid-template-rows: repeat(auto-fill, 32px);
  justify-content: space-between;
  row-gap: 2px;
}
.show-all-colors-btn {
  margin-top: 9.5px;
}

.icon-arrow-down-btn {
  width: 24px;
  height: 24px;
  display: block;
}

.icon-arrow-up-btn {
  display: block;
  width: 24px;
  height: 24px;
  transform: rotate(180deg);
}

.color-dot-box {
  width: 32px;
  height: 32px;
  display: flex;
  cursor: pointer;
}

.color-dot {
  margin: auto;
  width: 24px;
  height: 24px;
  border-radius: 100%;
  display: inline-block;
}
</style>
