<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png" />
        <ChampionsList/>
    </div>
</template>

<script>
import ChampionsList from "./components/ChampionsList.vue";

export default {
    name: "app",
    components: {
        ChampionsList
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
