<template>
    <div class="film-container flex"> 
        <ul class="single-film flex" v-for="(film, index) in filmsList" v-bind:key="index">
            <li>{{ film.title }}</li>
            <li>{{ film.original_title }}</li>
            <li v-if="film.original_language === 'it'">{{ film.original_language }} <img class="flag" src="../assets/flagsImg/it.png" alt=""> </li>
            <li v-else-if="film.original_language === 'en'">{{ film.original_language }} <img class="flag" src="../assets/flagsImg/en.png" alt=""></li>
            <li v-else>{{ film.original_language }}</li>
            <li>{{ film.vote_average }}</li>
        </ul>
    </div>
    
</template>

<script>
export default {
    name: "Main",
    props: ["filmsList"],

} // export default
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
}

.single-film li img {
    width: 20px;
    height: 20px;
    padding: 2px;
}



</style>