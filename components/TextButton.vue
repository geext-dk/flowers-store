<template>
  <button class="text-btn" @click="onButtonClicked()">
    <div
      :style="{ display: showLeftIcon ? 'inline-block' : 'none' }"
      class="text-btn-left-icon"
    >
      <slot name="left-icon"></slot>
      <div class="text-btn-left-icon-hover-active"></div>
    </div>
    <div class="text-btn-text-container">
      <div class="text-btn-text"><slot></slot></div>
      <div class="text-btn-text-underline"></div>
    </div>
    <div
      :style="{ display: showRightIcon ? 'inline-block' : 'none' }"
      class="text-btn-right-icon"
    >
      <slot name="right-icon"></slot>
    </div>
  </button>
</template>

<script>
export default {
  computed: {
    showLeftIcon() {
      return !!this.$slots['left-icon']
    },
    showRightIcon() {
      return !!this.$slots['right-icon']
    },
  },
  methods: {
    onButtonClicked() {
      this.$emit('click')
    },
  },
}
</script>

<style scoped>
.text-btn {
  all: unset;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  height: 32px;
  cursor: pointer;
  user-select: none;
}

.text-btn-text {
  margin-top: 4px;
}

.text-btn-text-underline {
  height: 0px;
  width: 100%;
  border: 2px solid transparent;
  border-radius: 2px;
}

.text-btn:hover .text-btn-text-underline {
  border-color: #a3c8ea;
  background-color: #a3c8ea;
}

.text-btn:active .text-btn-text-underline {
  border-color: #5297d7;
  background-color: #5297d7;
}

.text-btn-left-icon-hover-active {
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

.text-btn:hover .text-btn-left-icon-hover-active {
  display: block;
  border-color: #5297d7;
}

.text-btn:active .text-btn-left-icon-hover-active {
  display: block;
  border-color: #2566a1;
}

.text-btn-left-icon {
  width: 50px;
  height: 50px;
  position: relative;
}
</style>
