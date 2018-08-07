<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>

    <div id="chartdiv" style="width: 100%; height: 400px;"></div>

    <h2>Essential Links</h2>
    <ul>
      <li>
        <a href="https://vuejs.org" target="_blank">Core Docs</a>
      </li>
      <li>
        <a href="https://forum.vuejs.org" target="_blank">Forum</a>
      </li>
      <li>
        <a href="https://gitter.im/vuejs/vue" target="_blank">Gitter Chat</a>
      </li>
      <li>
        <a href="https://twitter.com/vuejs" target="_blank">Twitter</a>
      </li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li>
        <a href="http://router.vuejs.org/" target="_blank">vue-router</a>
      </li>
      <li>
        <a href="http://vuex.vuejs.org/" target="_blank">vuex</a>
      </li>
      <li>
        <a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a>
      </li>
      <li>
        <a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      msg: 'Welcome to Your Vue.js + amCharts App'
    }
  },
  created () {
    AmCharts.makeChart("chartdiv",
      {
        "path": "dist/amcharts/",
        "type": "serial",
        "categoryField": "type",
        "chartCursor": {},
        "graphs": [
          {
            "type": "column",
            "title": "Pizza types",
            "valueField": "sold",
            "fillAlphas": 0.8
          }
        ],
        "dataProvider": [
          { "type": "Margherita", "sold": 120 },
          { "type": "Funghi", "sold": 82 },
          { "type": "Capricciosa", "sold": 78 },
          { "type": "Quattro Stagioni", "sold": 71 }
        ]
      }
    );
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
