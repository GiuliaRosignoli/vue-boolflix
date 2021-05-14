<template>
    <div class="film-container flex"> 
        <div class="if flex" v-if="this.filmsList.length > 0">            
            <ul class="single-film flex" v-for="(film, index) in filmsList" v-bind:key="index">
                <div class="poster" v-if="film.poster_path" v-bind:style="{ backgroundImage: 'url(https://image.tmdb.org/t/p/w342' + film.poster_path + ')'}">
                </div>
                <div v-else class="placeholder poster" v-bind:style="{ backgroundImage: 'url(https://www.altavod.com/assets/images/poster-placeholder.png)'}">Title: {{ film.title }} {{film.name}}</div>
                <div class="overlay">
                    <li>Title: {{ film.title }} {{film.name}}</li>
                    <li v-show="film.original_title !== film.title">Original Title: {{ film.original_title }}</li>
                    <li v-if="film.original_language === 'it'">Language: {{ film.original_language }} <img class="flag" src="../assets/flagsImg/it.png" alt=""> </li>
                    <li v-else-if="film.original_language === 'en'">Language: {{ film.original_language }} <img class="flag" src="../assets/flagsImg/en.png" alt=""></li>
                    <li v-else>Language: {{ film.original_language }}</li>
                    <i class="fas fa-star" v-for="i in getStars(film.vote_average)" :key="`full-${i}`"></i>
                    <i class="far fa-star" v-for="i in 5 - getStars(film.vote_average)" :key="`empty-${i}`"></i>
                    <li class="overview">Overview: {{ film.overview }}</li>
                </div>
            </ul>
        </div>
        <div class="result-cont" v-else> <!-- No results found - message -->
            <div class="no-results"> Oh darn. We don't have that. Try searching for another film or series.</div>
        </div>
    </div>
    
</template>

<script>
export default {
    name: "Main",
    props: ["filmsList"],
    methods: {
        getStars(rate){
           return Math.ceil(rate /2);
         },
    }
   
} // export default
</script>

<style lang="scss" scoped>
@import "../styles/general.scss"; 
@import "../styles/vars.scss";
@import "../styles/utilities.scss";


.film-container {
    padding-top: 2rem;
}


.if {
    justify-content: center;
    flex-wrap: wrap;
    width: 100%;
}

.single-film {
    position: relative;
    justify-items: center;
    flex-direction: column;
    flex-basis: calc(100% / 5 - 20px);
    height: 195px;
    margin-bottom: 20px;
    margin: 0.2rem; 
    font-size: 0.9rem;
    cursor: pointer;
    .poster {
        width: 100%;
        height: 100%;
       background-size: cover;
    }
   .overlay {
       position: absolute;
       height:100%;
       width:100%;
       padding: 7px;
       opacity: 0;
       overflow-y: auto;
       transition: background-color 0.3s ease-in-out;
       &:hover {
       background:rgba(0,0,0,0.6);
       opacity: 1;
       .overview {
           padding-top: 0.7rem;
           font-size: 0.6rem;
            }
        }
   } /*overlay */
   
} /* single-film */

.placeholder.poster {
    background-size: cover;
    background-position: center;
    color: $deepblue;
}
.single-film li img {
    width: 20px;
    height: 20px;
    padding: 3px;
}

.no-results {
    padding: 5rem;
    font-size: 1.8rem;
}

.fas {
    color: yellow;
}


</style>