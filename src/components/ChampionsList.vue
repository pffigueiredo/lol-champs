<template>
    <div>
        <main class="champions-grid">
            <div v-for="champion in championsJSON" :key="championsJSON[champion]">
              <Champion :champion="champion" />
            </div>
        </main>
    </div>
</template>

<script>
 import json from '../assets/en_us_TFT.json'
import Champion from "../components/Champion";

export default {
    name: "ChampionsList",
    components:{
        Champion
    },
    data() {
        return {
            championsJSON: json.champions,
            traits: []
        };
    },
    methods: {
        getTraits : function() {
            var self = this;
             for(var champion in self.championsJSON){
                self.championsJSON[champion].traits.forEach(t => {

                    if(!self.traits.includes(t)){
                        self.traits[t] = [self.championsJSON[champion].name];
                    }else{
                        self.traits[t].push(self.championsJSON[champion].name);
                    }
                        
                })
             }
        }
    },
    mounted() {
        this.getTraits();
        this.traits.push("dasda");
    }

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  .champions-grid{
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-row-gap: 20px;
  }

</style>
