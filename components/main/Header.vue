<template>
  <header class="main-header">
    <div class="main-header-logo">
      <icon-flowers-store-logo class="main-logo" />
    </div>
    <nav class="main-header-nav">
      <text-button>букеты</text-button>
      <text-button>цветы поштучно</text-button>
      <text-button>комнатные растения</text-button>
      <text-button>подарки</text-button>
    </nav>
    <div class="main-header-order-info"></div>
    <div class="main-header-profile-buttons"></div>
  </header>
</template>

<script>
import TextButton from '../TextButton.vue'
export default {
  components: {
    TextButton,
  },
}
</script>

<style>
.main-header {
  height: 72px;
  width: 100%;
  display: flex;
  justify-content: space-evenly;
  align-content: center;
}

.main-header-logo {
  display: grid;
  justify-content: center;
  align-content: center;
}

.main-logo {
  height: 64px;
  width: 64px;
}

.main-header-nav {
  display: flex;
  justify-content: space-between;
  align-content: stretch;
  align-items: center;
}
</style>
