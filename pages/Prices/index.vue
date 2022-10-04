<template>
  <div>
    <Price v-for="price in prices" :key="price.symbol" :symbol="price.symbol" :lastprice="price.lastprice"/>
  </div>
</template>

<script>
import axios from 'axios';
import Price from '../../components/Price';

export default {
  data() {
    return {
      prices: null
    };
  },
  async created() {
    try {
      const res = await axios.get("https://api2.binance.com/api/v3/ticker/24hr");
      console.log("created prices", res.data)
      this.prices = res.data;
      console.log(res.data);
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
