<template>
    <div>
        <header>
            <h1>League of Legends Champions</h1>
        </header>
        <main class="champions-grid">
            <div class="champion" v-for="champion in championsArr" v-bind:key="champion.id">
                {{champion.name}}
            </div>
        </main>
    </div>
</template>

<script>
import axios from "axios";

export default {
    name: "ChampionsList",
    data() {
        return {
            championsArr: []
        };
    },
    mounted() {
        axios
            .get(
                "http://ddragon.leagueoflegends.com/cdn/6.24.1/data/en_US/champion.json"
            )
            .then(response => {
                for (var item in response.data.data) {
                    this.championsArr.push(response.data.data[item]);
                }
            });
    }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  .champions-grid{
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))
  }

</style>
