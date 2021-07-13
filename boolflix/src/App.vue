<template>
  <div id="app">
    <Header @searchEmit="searchFunction"/>
    <Main :movieList="movies" :seriesList="series"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import axios from "axios";

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
    return {
      apiKey: "498d1c8d4b0a878ee9fc00ed9888ae18",
      apiLang: "it-IT",
      movies: [],
      series: []
    }
  },
  methods: {
    searchFunction(searched) {

      axios
                .get(`

                    https://api.themoviedb.org/3/search/movie?api_key=${this.apiKey}&language=${this.apiLang}&query=${searched}

                    `)
                .then (outcome => {
                    this.movies = outcome.data.results;
                    console.log(this.movies)

                })
                .catch(err=> { 
                    console.log(err)
                })

      axios
                .get(`

                     https://api.themoviedb.org/3/search/tv?api_key=${this.apiKey}&language=${this.apiLang}&query=${searched}

                    `)
                .then (outcome => {
                    this.series = outcome.data.results;
                    console.log(this.series)

                })
                .catch(err=> { 
                    console.log(err)
                })

    },
  }
}
</script>

<style lang="scss">
@import "@/styles/commons.scss";
</style>
