<template>
  <div id="app">
    <Body />
    <Footer />
  </div>
</template>

<script lang="ts">
import Footer from "./components/Footer.vue";
import Body from "./components/Body.vue";

export default ({
  components: {
    Footer,
    Body,
  },
})

</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap');
html, body {
  height: 100%;
  margin: 0;
  font-family: 'Inter', sans-serif;
}

</style>
