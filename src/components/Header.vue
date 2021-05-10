<template>
    <div class="wrapper flex">
         <a href="#">
            <img v-bind:src="logo" alt="logo">
         </a>
         <div class="filler"></div>
        <input type="text" placeholder="Search film"  v-model.trim ="searchFilm">
        <button @click="$emit('startingSearch', searchFilm)">Search</button>
    </div>
    
</template>

<script>


export default {
    name: "Header",
    data(){
        return {
            searchFilm: "",
            logo: "https://fontmeme.com/permalink/210510/3f37c13a0705940786b250f7aaa9cafa.png",
        }
    },
    
}
</script>

<style lang="scss" scoped>
@import "../styles/general.scss"; 
@import "../styles/vars.scss";
@import "../styles/utilities.scss";

.wrapper {
    
    align-content: center;
    a {
        img {
            width: 14rem;
            margin: 0.5rem;
            padding: 0.8rem;
        }
    }
    input {
        align-self: center;
        margin-right: 1rem;
        padding: 8px;
        width: 20rem;
        max-width: 100%;
        height: 2.4rem;
        max-height: 100%;
        background-color: $lighterpurple;
        color: $darkerpurple;

    }
    button {
        align-self: center;
        width: 4rem;
        padding: 8px 8px;
        margin-right: 3rem;
        height: 2.4rem;
        padding: 5px;
        background-color: $purple-1;
        font-weight: bold;
        color: $lighterpurple;
        &:hover {
            transform: scale(1.3);
        }
    }
}

.filler {
    flex-grow: 1;
}

</style>