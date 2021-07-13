<template>
  <main>
      <ul v-if="this.movies.length > 0">
          <li v-for="(e, i) in movies" :key="i" class="primary"> 
              
              {{e.title}}

              <ul>
                  <li class="secondary">
                      Titolo originale: {{e.original_title}}
                  </li>
                  <li class="secondary">
                      Lingua originale: {{e.original_language}}
                  </li>
                  <li class="secondary">
                      voto: {{e.vote_average}}
                  </li>
              </ul>

          </li>
      </ul>
  </main>
</template>

<script>
import axios from "axios";

export default {
    name: "Main",
    props: {
       details: String,
    },
    data() {
        return {
            apiURL: "https://api.themoviedb.org/3/search/movie?",
            apiKey: "498d1c8d4b0a878ee9fc00ed9888ae18",
            apiLang: "it-IT",
            apiQuery: this.details,
            movies: []
        }
    },
    created() {
        this.getMovie();
    },
    methods: {
        getMovie() {
            axios
                .get(`

                    ${this.apiURL}api_key=${this.apiKey}&language=${this.apiLang}&query=${this.details}

                    `)
                .then (x => {
                    this.movies = x.data.results;
                    console.log(this.apiQuery)

                })
                .catch(err=> { 
                    console.log(err)
                })
        }
    }
}
</script>

<style>

ul {
    color:white;
    width: 50%;
    margin:auto;
    list-style-type: none;
}

li.primary {
    font-size: 1.8rem;
}

li.secondary {
    font-size: 1.3rem;
    padding:20px;
}

</style>

++++++++++NOTE++++++++++
API con i popular: "https://api.themoviedb.org/3/movie/popular?api_key=498d1c8d4b0a878ee9fc00ed9888ae18"