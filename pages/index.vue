<template>
  <div>
    <div v-for="result in results" :key="result.symbol">
      {{result.symbol}}
    </div>
    Welcome to Mammeta
  </div>
</template>

<script>
import axios from 'axios'

export default {
    data() {
      return {
      results: null
    }
  }
    ,
    head() {
        return {
            title: 'Welcome to Dexter',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Dexter Home'
                }
            ]
        };
    },
    
    async mounted () {
      console.log("i'm created");
      const res= await axios.get('https://api2.binance.com/api/v3/ticker/24hr')
      console.log(res.data);
      this.results=res.data;
    }


};
</script>
