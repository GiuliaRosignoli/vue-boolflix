<template>
<div class="relative"> 
    <div class="header wrapper flex">
         <a href="./home">
            <img v-bind:src="logo" alt="logo">
         </a>
         <div class="filler"></div>
        <input type="text" placeholder="Search film"  v-model.trim ="searchFilm">
        <button @click="$emit('startingSearch', searchFilm)">Search</button>
        <button class="right" @click="resetInputField">Reset</button>
    </div>
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
    methods: {
        resetInputField(){
            console.log("test")
          this.searchFilm = "";
   
        
        }
    }
    
    
}
</script>

<style lang="scss" scoped>
@import "../styles/general.scss"; 
@import "../styles/vars.scss";
@import "../styles/utilities.scss";


.header.wrapper {
    position: fixed;
    top: 0;
    right: 0;
    left: 0;
    width: 100%;
    height: 90px;
    align-content: center;
    background-color: $deepblue;
    z-index: 10;
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
        width: 9.5rem;
        max-width: 100%;
        height: 1.6rem;
        max-height: 100%;
        background-color: $lighterpurple;
        color: $darkerblue;
        &:hover {
            background-color: #fff;
        }

    }
    button {
        align-self: center;
        width: 3.8rem;
        margin: 0.4rem;
        padding: 8px 8px;
        height: 2.1rem;
        padding: 5px;
        background-color: $purple-1;
        font-weight: bold;
        color: $lighterpurple;
        &:hover {
        transform: scale(1.3);
        background-color: $lighterpurple;
        color: $darkerblue;
            }
        }
        
    
    button.right {
        margin-right: 3rem;
        width: 2.7rem;
        height: 1.6rem;
        font-size: 0.5rem;
    }
}

.filler {
    flex-grow: 1;
}

</style>