<template>
    <div>
    
        <ul v-for="(film, index) in filmsList" v-bind:key="index">
            <li>{{ film.title}}</li>
            <li>{{ film.original_title}}</li>
            <li>{{ film.original_language}}</li>
            <li>{{film.vote_average}}</li>
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