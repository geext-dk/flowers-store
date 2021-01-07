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
    <div class="main-header-order-info">
      <text-button>
        <template v-slot:left-icon>
          <icon-phone-call class="phone-call-icon" />
        </template>
        57-13-99
      </text-button>
      <text-button>
        <template v-slot:left-icon>
          <icon-shipping-car class="icon-shipping-car" />
        </template>
        доставка
      </text-button>
    </div>
    <div class="main-header-profile-buttons">
      <profile-button />
      <shopping-cart-button :items-amount="14" />
    </div>
  </header>
</template>

<script>
import ShoppingCartButton from '../ShoppingCartButton.vue'
import TextButton from '../TextButton.vue'
import ProfileButton from '../ProfileButton.vue'
import IconPhoneCall from '../icons/IconPhoneCall.vue'
import IconShippingCar from '../icons/IconShippingCar.vue'
export default {
  components: {
    TextButton,
    ShoppingCartButton,
    ProfileButton,
    IconPhoneCall,
    IconShippingCar,
  },
}
</script>

<style scoped>
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
  align-content: stretch;
  align-items: center;
  gap: 48px;
}

.main-header-order-info {
  display: flex;
  gap: 32px;
  align-content: stretch;
  align-items: center;
}

.main-header-profile-buttons {
  display: flex;
  gap: 32px;
  align-content: stretch;
  align-items: center;
}

.phone-call-icon {
  width: 22px;
  height: 22px;
}

.icon-shipping-car {
  width: 22px;
  height: 19px;
}
</style>
