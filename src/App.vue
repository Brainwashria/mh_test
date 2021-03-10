<template>
  <div id="app">
  <currencyTable/>
  </div>
</template>

<script>
import currencyTable from './components/currencyTable'
export default {
  name: 'App',
  components: {
  currencyTable
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
