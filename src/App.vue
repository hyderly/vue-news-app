<template>
  <div id="app">
    <NewsTable/>
  </div>
</template>

<script>

import NewsTable from './components/NewsTable.vue';
import Vue from 'vue';
import axios from 'axios';
import VueAxios from 'vue-axios';

Vue.use(VueAxios, axios);




export default {
  name: 'App',
  components: {
    NewsTable
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
  padding: 0 50px;
}
</style>
