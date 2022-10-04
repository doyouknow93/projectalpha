<template>
  <div>
    <h1>About Dexter</h1>
    <p>How is Dexter?</p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'About Us',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'About Dexter'
        }
      ]
    };
  }
};
</script>
