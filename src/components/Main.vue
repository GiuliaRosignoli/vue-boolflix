<template>
    <div>{{ filmsList}}</div>
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