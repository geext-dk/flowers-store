<template>
  <div class="container">
    <div class="single-flowers-container">
      <flower-card
        v-for="flower in flowers"
        :key="flower.id"
        v-bind="flower"
        class="flower-card"
      />
    </div>
  </div>
</template>

<script>
import FlowerCard from '~/components/FlowerCard.vue'
export default {
  components: {
    FlowerCard,
  },
  data() {
    return {
      flowers: [
        {
          id: 1,
          title: 'Роза',
          price: 79,
          originalPrice: 140,
          imageUrl: require('../assets/images/Rose.png'),
        },
        {
          id: 2,
          title: 'Тюльпан',
          price: 59,
          originalPrice: 130,
          imageUrl: require('../assets/images/Tulip.png'),
        },
        {
          id: 3,
          title: 'Лилия',
          price: 99,
          originalPrice: 160,
          imageUrl: require('../assets/images/Lilly.png'),
        },
        {
          id: 4,
          title: 'Гербера',
          price: 55,
          originalPrice: 100,
          imageUrl: require('../assets/images/Herber.png'),
        },
        {
          id: 5,
          title: 'Пион',
          price: 129,
          originalPrice: 200,
          imageUrl: require('../assets/images/Pion.png'),
        },
        {
          id: 1,
          title: 'Гвоздика',
          price: 79,
          originalPrice: 130,
          imageUrl: require('../assets/images/Gvozdika.png'),
        },
      ],
    }
  },
}
</script>

<style>
@font-face {
  font-family: 'Gilroy-Regular';
  src: url(../assets/fonts/Gilroy-Regular.woff2);
}

body {
  font-family: 'Gilroy-Regular';
  font-size: 16px;
  box-sizing: border-box;
}

.flower-card {
  margin: 10px;
}

.container FlowerCard {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

.single-flowers-container {
  display: flex;
  flex-basis: max-content;
  gap: 16px;
}
</style>
