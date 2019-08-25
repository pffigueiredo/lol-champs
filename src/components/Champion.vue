<template>
    <div class="champion">
       {{champion.name}}
        <img :src="require('../assets/' + champion.splash)" />
    </div>
</template>

<script>
export default {
    name: "Champion",
    props: ["champion"]
};
</script>

<style lang="scss" scoped>
.champion {
    display: grid;
    grid-template-rows: 1fr min-content;
    justify-content: center;
}
</style>