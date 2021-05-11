<template>
    <div class="film-container flex"> 
        <div class="if flex" v-if="this.filmsList.length > 0"> 
            <ul class="single-film flex" v-for="(film, index) in filmsList" v-bind:key="index">
                <li>Title: {{ film.title }} {{film.name}}</li>
                <li v-show="film.original_title !== film.title">Original Title: {{ film.original_title }}</li>
                <li v-if="film.original_language === 'it'">Language: {{ film.original_language }} <img class="flag" src="../assets/flagsImg/it.png" alt=""> </li>
                <li v-else-if="film.original_language === 'en'">Language: {{ film.original_language }} <img class="flag" src="../assets/flagsImg/en.png" alt=""></li>
                <li v-else>Language: {{ film.original_language }}</li>
                <li>{{ film.vote_average }}</li>
            </ul>
        </div>
        <div class="result-cont flex" v-else>
            <h3 class="no-results">Oh darn. We don't have that. Try searching for another film or series</h3>
        </div>
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



.if {
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