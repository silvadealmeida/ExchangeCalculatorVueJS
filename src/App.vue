<template>
  <div id="app">
    <h1 class="textCenter">Exchange Rate Converter</h1>
    <div class="line">
    <Converter currencyA="USD" currencyB="BRL"/>
    <Converter currencyA="BRL" currencyB="USD"/>
    </div>
    <div class="line">
    <Converter currencyA="EUR" currencyB="BRL"/>
    <Converter currencyA="BRL" currencyB="EUR"/>
    </div>
    
  </div>
</template>

<script>

import Converter from  "./components/Converter.vue"
export default {
  name: 'App',
  components: {
    Converter
  }
}
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.line{
  margin-top: 40px;
  display: flex;
  justify-content: space-around;
}
.textCenter{
  text-align: center;
}
</style>
