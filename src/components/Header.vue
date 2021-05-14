<template>
<div class="relative"> 
    <div class="header wrapper flex">
         <a href="./home">
            <img v-bind:src="logo" alt="logo">
         </a>
         <ul class="menu flex">
             <li><a href="./home">Home</a></li>
             <li><a href="#">TV Shows</a></li>
             <li><a href="#">Movies</a></li>
             <li><a href="#">Latest</a></li>
             <li><a href="#">My List</a></li>
         </ul>
         <div class="filler"></div>
        <input type="text" placeholder=" Search"  v-model.trim ="searchFilm">
        <button @click="$emit('startingSearch', searchFilm)">Search</button>
        <button class="right" @click="resetInputField">Reset</button>
         <a id="kids-icon" href="#">Kids</a>
        <div class="box"><img src="../assets/GiuliaRosignoli.jpg" alt=""></div>
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

    /* First list -menu */
    .menu {
        align-self: center;
        padding-left: 0.9rem;
       li {
            padding-right: 0.7rem;
            cursor: pointer;
       }
    }

    #kids-icon {
        align-self: center;
        margin-right: 1.7rem;
        padding-left: 1.1rem;
    }
    input {
        align-self: center;
        margin-right: 1rem;
        padding: 8px;
        width: 9.5rem;
        max-width: 100%;
        height: 1.6rem;
        max-height: 100%;
        background-color: $deepblue;
        color: $white;
        border: 1px solid $white;
        &:hover {
            background-color: #fff;
            color: $deepblue;
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
        color: $white;
        cursor: pointer;
        &:hover {
        transform: scale(1.3);
        background-color: $lighterpurple;
        color: $white
            }
        }
        
    
    button.right {
        margin-right: 0.8rem;
        width: 2.7rem;
        height: 1.6rem;
        font-size: 0.5rem;
    }
}

.box {
    align-self: center;
    width: 2.6rem;
    height: 2.6rem;
    margin-right: 1rem;
    cursor: pointer;
    img {
        max-width: 100%;
        max-height: 100%;
    }
}

</style>