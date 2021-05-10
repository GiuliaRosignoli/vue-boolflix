<template>
    <h2 v-for="(film, index) in films" v-bind:key="index">{{ filmsList.title}}</h2>
</template>

<script>
export default {
    name: "Main",
    props: ["filmsList"],

}
</script>

<style lang="scss" scoped>
@import "../styles/general.scss"; 
@import "../styles/vars.scss";
@import "../styles/utilities.scss";

</style>