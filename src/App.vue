<template>
  <div id="app">
    <Header 
    :generi="allGenres" @changeSelect="filtraDischi"/>
    <Dischi @generiReady="generiMet"  :genere = genereSelect />
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
  },
  data: function () {
    return {
      genereSelect: '',
      allGenres: []
    }
  },
  methods: {
    filtraDischi: function(select) {
      this.genereSelect = select;
    },
    generiMet: function(array) {
      this.allGenres = array;
    }
  },
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
