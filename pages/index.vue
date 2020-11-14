<template>
  <client-only>
    <trading-vue :data="tradingVue" :overlays="overlays"></trading-vue>
  </client-only>
</template>

<script>
import SetupIndicator from '~/components/SetupIndicator';
// Importing manually will also throw `windows is not defined error`
// Using `components: true` in nuxt.config.js
// import TradingVue from 'trading-vue-js'
export default {
  name: 'app',
  // Importing manually will also throw `windows is not defined error`
  // Using `components: true` in nuxt.config.js
  // components: { TradingVue }
  data() {
    return {
      tradingVue: {
        chart: {
          type: 'Candles',
          data: [
            [ 1551128400000, 33,  37.1, 14,  14,  196 ],
            [ 1551132000000, 13.7, 30, 6.6,  30,  206 ],
            [ 1551135600000, 29.9, 33, 21.3, 21.8, 74 ],
            [ 1551139200000, 21.7, 25.9, 18, 24,  140 ],
            [ 1551142800000, 24.1, 24.1, 24, 24.1, 29 ],
          ],
          indexBased: true,
          tf: '1d',
        },
        onchart: [
          {
            name: 'Setups',
            type: 'Setups',
            data: [[1551128400000, 1, 35]],
            settings: {},
          },
        ],
      },
      overlays: [SetupIndicator]
    }
  }
}
</script>
