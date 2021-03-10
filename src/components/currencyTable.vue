<template>
  <table>
    <thead>
    <tr class="table-header">
      <th>Валюта</th>
      <th>Цена</th>
      <th>Количество</th>
    </tr>
    </thead>
    <tr v-for="row in this.currencyArray" :key="row.name">
      <td>{{row.name}}</td>
      <td>{{row.volume}}</td>
      <td>{{(row.price.amount).toFixed(2)}}</td>
    </tr>
  </table>
</template>

<script>
import axios from 'axios';
export default {
  name: "currencyTable",
  data: function() {
    return {
      currencyArray: []
    }
  },
  mounted() {
    axios.get('http://phisix-api3.appspot.com/stocks.json').then(response => {
      this.currencyArray = response.data.stock;
    }).catch(e => {
      alert(`Error: ${e.message}`)
    })
  }
}
</script>

<style scoped lang="less">
  table {
    font-size: 20px;
    thead {
      background-color: black;
      color: white;
    }
    td, th {
      width: 250px;
      height: 50px;
    }
  }
</style>