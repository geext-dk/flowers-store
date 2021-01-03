<template>
  <button class="btn" @click="onButtonClicked()">
    <div class="btn-text-container">
      <div class="btn-text"><slot></slot></div>
      <div class="btn-text-underline"></div>
    </div>
    <div class="btn-icon"><slot name="icon"></slot></div>
  </button>
</template>

<style>
.btn {
  all: unset;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  height: 32px;
  cursor: pointer;
}

.btn-text {
  margin-top: 4px;
}

.btn-text-underline {
  height: 4px;
  width: 100%;
}

.btn-text-underline {
  height: 0px;
  border: 2px solid transparent;
  border-radius: 2px;
}

.btn:hover .btn-text-underline {
  border-color: #a3c8ea;
  background-color: #a3c8ea;
}

.btn:active .btn-text-underline {
  border-color: #5297d7;
  background-color: #5297d7;
}
</style>

<script>
export default {
  methods: {
    onButtonClicked() {
      this.$emit('click')
    },
  },
}
</script>
