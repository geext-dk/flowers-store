<template>
  <div class="profile-btn">
    <icon-profile class="profile-btn-icon" />
    <div class="shopping-cart-hover-active"></div>
  </div>
</template>

<script>
import IconProfile from './icons/IconProfile.vue'
export default {
  components: {
    IconProfile,
  },
}
</script>

<style scoped>
.profile-btn {
  position: relative;
  width: 50px;
  height: 70px;
  cursor: pointer;
  user-select: none;
}

.profile-btn-icon {
  position: absolute;
  width: 22px;
  height: 20px;
  left: calc(50% - 22px / 2);
  top: calc(50% - 20px / 2 - 1px);
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

.profile-btn:hover .shopping-cart-hover-active {
  display: block;
  border-color: #5297d7;
}

.profile-btn:active .shopping-cart-hover-active {
  display: block;
  border-color: #2566a1;
}
</style>
