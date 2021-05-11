<template>
    <div class="flex">
    
        <ul class="film-list flex" v-for="(film, index) in filmsList" v-bind:key="index">
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


.film-list {
    width: 100%;
    flex-direction: column;
    li {
        justify-items: center;
        flex-basis: calc(100% / 6 - 10px);
        margin-bottom: 10px;
    }
}

</style>