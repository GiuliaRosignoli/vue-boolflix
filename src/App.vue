<template>
  <div id="app">
  
      <header>
       <Header @startingSearch="handler"  />
    </header>

    <main>
      <Main v-bind:filmsList="films.concat(series)"  @goBacktoTrending="callApiTrending"/>
    </main>
    
    
    <footer>
      <Footer />
    </footer>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import Footer from './components/Footer.vue';
import axios from 'axios';


export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer,
  },
   data(){
        return {
            apiURL: "https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=",
            apiSeriesURL: "https://api.themoviedb.org/3/search/tv?api_key=e99307154c6dfb0b4750f6603256716d&query=", //2nd axios call
            apiTrendingURL: "https://api.themoviedb.org/3/trending/movie/week?api_key=e99307154c6dfb0b4750f6603256716d",
            films: [],
            series: [],
            } // return
    }, // data
    created(){
      this. callApiTrending()
    },
    
    methods: {
        getFilm(searchFilm) {
            axios.get(this.apiURL + searchFilm)
            .then(res=>{
                console.log(res.data);
                 this.films=[];
                this.films= res.data.results;
            
              //  console.log(this.films)
            })
            .catch(err=>{
             console.log('Error:', err)
            })
        }, //getFilm

        // gET TV Series - 2nd Axios method
        getSeries(searchFilm) {
            axios.get(this.apiSeriesURL + searchFilm)
            .then(res=>{
                console.log(res.data);
                this.series= res.data.results;
              //  console.log(this.films)
            })
            .catch(err=>{
               console.log('Error:', err)
            })
        }, //getSeries

         handler(searchFilm){
              this.getFilm(searchFilm);
              this.getSeries(searchFilm);
         },

         callApiTrending(){
           axios.get(this.apiTrendingURL)
        .then(res=>{
            console.log(res.data);
            this.films= res.data.results;    
          //  console.log(this.films)
        })
        .catch(err=>{
            console.log('Error:', err)
        })
         }
         
       
    }, // methodS section ends here
} //export default
</script>


<style lang="scss">
@import "./styles/general.scss"; 
@import "./styles/vars.scss";
@import "./styles/utilities.scss";

#app { 
  padding-top: 90px; 
}

main {
  background-color: #020733; 
   height: calc(100vh - 170px);
  overflow-y: auto;
}


</style>
