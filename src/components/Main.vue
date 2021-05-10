<template>
    <div>
        <ul>
            <li v-for="(film, index) in films" v-bind:key="index">{{ filmsList.title}}</li>
        </ul>
    </div>
    
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