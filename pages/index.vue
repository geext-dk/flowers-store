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
          colors: [
            {
              color: '#ed488e',
            },
            {
              color: '#803656',
            },
            {
              color: '#D490C1',
            },
            {
              color: '#A11639',
            },
            {
              color: '#AB426D',
            },
          ],
        },
        {
          id: 2,
          title: 'Тюльпан',
          price: 59,
          originalPrice: 130,
          imageUrl: require('../assets/images/Tulip.png'),
          colors: [
            {
              color: '#c0165d',
            },
            {
              color: '#782F46',
            },
            {
              color: '#ED7A94',
            },
            {
              color: '#DC8FAB',
            },
            {
              color: '#FCBDDE',
            },
            {
              color: '#E1B08C',
            },
            {
              color: '#E1B08C',
            },
            {
              color: '#858AC9',
            },
            {
              color: '#6C8BE4',
            },
            {
              color: '#90C8FC',
            },
            {
              color: '#E3D3D0',
            },
          ],
        },
        {
          id: 3,
          title: 'Лилия',
          price: 99,
          originalPrice: 160,
          imageUrl: require('../assets/images/Lilly.png'),
          colors: [
            {
              color: '#c0165d',
            },
            {
              color: '#782F46',
            },
            {
              color: '#ED7A94',
            },
            {
              color: '#DC8FAB',
            },
            {
              color: '#FCBDDE',
            },
            {
              color: '#E1B08C',
            },
            {
              color: '#E1B08C',
            },
            {
              color: '#858AC9',
            },
            {
              color: '#6C8BE4',
            },
            {
              color: '#90C8FC',
            },
            {
              color: '#E3D3D0',
            },
          ],
        },
        {
          id: 4,
          title: 'Гербера',
          price: 55,
          originalPrice: 100,
          imageUrl: require('../assets/images/Herber.png'),
          colors: [
            {
              color: '#d8afa7',
            },
            {
              color: '#E3D7D6',
            },
            {
              color: '#E3D7D6',
            },
          ],
        },
        {
          id: 5,
          title: 'Пион',
          price: 129,
          originalPrice: 200,
          imageUrl: require('../assets/images/Pion.png'),
          colors: [
            {
              color: '#fd90be',
            },
            {
              color: '#AB3565',
            },
            {
              color: '#FED4EE',
            },
          ],
        },
        {
          id: 1,
          title: 'Гвоздика',
          price: 79,
          originalPrice: 130,
          imageUrl: require('../assets/images/Gvozdika.png'),
          colors: [
            {
              color: '#e7d39b',
            },
            {
              color: '#E4DD9C',
            },
            {
              color: '#C18A5C',
            },
            {
              color: '#A11639',
            },
            {
              color: '#AB426D',
            },
          ],
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
