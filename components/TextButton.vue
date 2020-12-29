<template>
  <button class="btn" @click="onButtonClicked()">
    <div><slot></slot></div>
    <div class="btn-underline"></div>
  </button>
</template>

<style>
.btn {
  all: unset;
  display: inline-flex;
  flex-direction: column;
  cursor: pointer;
}

.btn-underline {
  visibility: hidden;
  border-radius: 1px;
  border-top: 1px solid #a3c8ea;
  border-bottom: 1px solid #a3c8ea;
  width: 100%;
  height: 0px;
}

.btn:hover .btn-underline {
  visibility: visible;
  border-color: #a3c8ea;
}

.btn:active .btn-underline {
  visibility: visible;
  border-color: #5297d7;
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
