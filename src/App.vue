<template>
  <div id="app">
    <Header />
    <Dischi />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Dischi from './components/Dischi.vue'

export default {
  name: 'App',
  components: {
    Header,
    Dischi
  }
}
</script>

<style lang="scss">
@import '~@fontsource/roboto/index.css';
@import '~@fontsource/roboto/700.css';
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  .container {
    width: 80%;
    margin: 0 auto;
    padding: 30px 0;
  }

  body {
    background-color: #1f2e3b;
    font-family: "Roboto";
  }
</style>
