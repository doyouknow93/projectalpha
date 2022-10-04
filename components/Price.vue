<template>
    <div class="price">
        <p>{{ price }}</p>
    </div>
</template>

<script>
export default {
    name: 'Price',
    props: ['symbol', 'lastPrice']
}
</script>

<style>
  .price {
    padding: 1 rem;
    border: 1px dotted #ccc;
    margin: 1rem 0;
  }
</style>