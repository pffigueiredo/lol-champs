<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png" />
        <HelloWorld msg="Welcome to Your Vue.js App" />
        {{json}}
    </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import axios from 'axios'

export default {
    name: "app",
    components: {
        HelloWorld
    },
    data(){
      return {
        json:""
      }
    },
    mounted() {
      axios.get('http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en_US/champion.json')
      .then((response) => this.json = response);
    }
};
</script>

<style>
#app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
