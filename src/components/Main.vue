<template>
    <div class="film-container flex"> 
        <ul class="single-film flex" v-for="(film, index) in filmsList" v-bind:key="index">
            <li>{{ film.title}}</li>
            <li>{{ film.original_title }}</li>
            <li>{{ film.original_language }}</li>
            <li>{{ film.vote_average }}</li>
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


.film-container {
    justify-content: center;
    flex-wrap: wrap;
    width: 100%;
}

.single-film {
    justify-items: center;
    flex-direction: column;
    flex-basis: calc(100% / 6 - 20px);
    padding: 10px;
    margin-bottom: 20px;
    background-color: lightblue
}

</style>