<template>
  <div class="price">
    <p>Symbol: {{ symbol }} 
      <br> Last price: {{ lastPrice }}
      <br> Volume: {{ volume }} 
      <br> Price Change %: {{ priceChangePercent }}</p>
  </div>
</template>

<script>
export default {
  name: 'Price',
  props: ['symbol', 'volume', 'priceChangePercent', 'lastPrice']
}
</script>

<style>
.price {
  padding: 1rem;
  border: 1px dotted #ccc;
  margin: 1rem 0;
}
</style>
