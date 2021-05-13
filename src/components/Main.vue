<template>
    <div class="film-container flex"> 
        <div class="if flex" v-if="this.filmsList.length > 0">                       <!--  :style="{ backgroundImage: `url(${member.coverImage})` }" -->       
                                                                            <!--v-bind:style="{ backgroundImage: 'url(' + image + ')' } -->
            <ul class="single-film flex" v-for="(film, index) in filmsList"   v-bind:key="index">
                <div class="poster" v-if="{ backgroundImage: 'url(' + 'https://image.tmdb.org/t/p/w342' + film.poster_path + ')' } !== { backgroundImage: 'url(' + 'https://image.tmdb.org/t/p/w342null' + film.poster_path + ')' } " v-bind:style="{ backgroundImage: 'url(' + 'https://image.tmdb.org/t/p/w342' + film.poster_path + ')' }"></div>
                <div v-else="{ backgroundImage: "url('../assets/placeholder.png') }" </div>
                <div class="overlay">
                    <li>Title: {{ film.title }} {{film.name}}</li>
                        <li v-show="film.original_title !== film.title">Original Title: {{ film.original_title }}</li>
                        <li v-if="film.original_language === 'it'">Language: {{ film.original_language }} <img class="flag" src="../assets/flagsImg/it.png" alt=""> </li>
                        <li v-else-if="film.original_language === 'en'">Language: {{ film.original_language }} <img class="flag" src="../assets/flagsImg/en.png" alt=""></li>
                        <li v-else>Language: {{ film.original_language }}</li>
                    <li>{{ film.vote_average }}</li>
                </div>
            </ul>
        </div>
        <div class="result-cont flex" v-else> <!-- No results found - message -->
            <div class="no-results">Oh darn. We don't have that. Try searching for another film or series.</div>
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
    position: relative;
    justify-items: center;
    flex-direction: column;
    flex-basis: calc(100% / 5 - 20px);
    height: 180px;
    margin-bottom: 20px;
    margin: 0.5rem; 
    .poster {
        width: 100%;
        height: 100%;
       background-size: cover;
    }
   .overlay {
       position: absolute;
       height:100%;
       width:100%;
       opacity: 0;
       transition: background-color 0.3s ease-in-out;
       &:hover {
       background-color: $deepblue;
       opacity: 1;
        }
   }
   
}

.single-film li img {
    width: 20px;
    height: 20px;
    padding: 2px;
}

.no-results {
    font-size: 1.8rem;
}


</style>