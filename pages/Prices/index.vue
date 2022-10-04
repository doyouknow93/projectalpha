<template>
  <div>
    <Price v-for="price in prices" :key="price.symbol" 
    :symbol="price.symbol" 
    :lastPrice="price.lastPrice"
    :volume="price.volume" 
    :priceChangePercent="price.priceChangePercent"/>
  </div>
</template>

<script>
import axios from 'axios';
import Price from '../../components/Price';

export default {
  data() {
    return {
      prices: []
    };
  },
  async created() {
    try {
      const res = await axios.get("https://api2.binance.com/api/v3/ticker/24hr");
      this.prices = res.data;
    } catch (err) {
      console.log(err);
    }
  },
  head() {
    return {
      title: "Prices",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Prices"
        }
      ]
    };
  },
  components: {Price}
};
</script>
