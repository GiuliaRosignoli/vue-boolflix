<template>
  <div id="app">
    <header>
       <Header @startingSearch="getFilm" 
              
       />
    </header>

    <main>
      <Main v-bind:filmsList="films"/>
    </main>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import axios from "axios";

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
   data(){
        return {
            apiURL: "https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=",
            films: [],
        }
    }, // Data

    methods: {
        getFilm(searchFilm) {
            axios.get(this.apiURL + searchFilm)
            .then(res=>{
                console.log(res.data);
                this.films= res.data.results;
              //  console.log(this.films)
            })
            .catch(err=>{
                console.log('Error:', err)
            })
        }, //getFilm
        
    } // method section ends here
} //export default
</script>

<style lang="scss">


</style>
